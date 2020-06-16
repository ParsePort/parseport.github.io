---
title: Services on Azure
#permalink: internal/
#has_children: true
#nav_order: 1
has_toc: false
---

# Container Registry
All docker images used by ParsePort are stored in the azure container registry: `parseport.azurecr.io`. The naming of the docker image reflects its purpose, and images named 'base' might not work individual, but only in collaboration with other images. Base images can minimize the build time and size of the resulting image, that uses the base image. Furthermore, base images can be used to control e.g. the OS version (if multiple images share a base).


# Web apps
A set of web apps / app services are consumed by the XBRL API, the flow is depicted in the diagram here:
![Flow for how the Linux services are used in the XBRL API solution](http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/ParsePort/ArchitecturalDocumentation/master/api-flow/linuxservices.txt?token=ANLMBL5MQKDJBT4XA4KUBLK66HG32 "Flow for how the Linux services are used in the XBRL API solution")

Overall information about setting up linux containers in app service, can be fund [`here`](https://techcommunity.microsoft.com/t5/azure-app-service/things-you-should-know-web-apps-and-linux/ba-p/392472)

## Linux services
The solution at https://github.com/ParsePort/ParsePort.XBRL.LinuxServices, contains the API and logic to combine a docker image for 4 different services. The C# code is constructed with a few configuration strings, to indicate which services that are available. The backend code contains logic to expose files generated in a docker container, in this setup the C# solution saves a set of files, which then are handled by a docker container, and when the new file is produced, the C# code can publish the result via the API.
For all docker servies, the producers, the setup uses a base image for setting up the environment, then there is a small docker image, using the base image, which executes a bash script to do what you would have done at a terminal.


* **iXBRLViewer** (https://linuxservices1.azurewebsites.net/)

Service to create a open source iXBRL viewer from any given taxonomy package. The input is a xHTML file and a set of taxonomy packages (zip files), the output is a HTML, including all CSS and Javascript. The docker container is constructed to watch for folders containing a xHTML with the same name of the folder, the container uses a batch script to do this operation.

[`bash file for the actual service behind the dotnet code`](https://github.com/ParsePort/DockerImages/blob/master/ixbrlviewerbuilder.sh)

* **html2pdf** (https://linuxservices2.azurewebsites.net/)

Service to convert html to pdf, the input file is a HTML, the output is pdf. The docker container is constructed to watch for files endning with `.html`, the container uses a batch script, and it is running a headless chrome to do this operation.

[`bash file for the actual service behind the dotnet code`](https://github.com/ParsePort/DockerImages/blob/master/watchforhtml.sh)

* **validation** (https://parseport-validation.azurewebsites.net/)

Service to validate XBRL, the input file is a zip file, the output is json or HTML. The docker container is constructed to watch for folders and look for `.zip` files in this folder. The validation is done via Arelle.

[`bash file for the actual service behind the dotnet code`](https://github.com/ParsePort/DockerImages/blob/master/arelle_validation.sh)

* **pdf2html** (https://linuxservices.azurewebsites.net/)

Service to convert PDF to HTML, the input file is a PDF, the output is HTML. The docker container is constructed to watch for files endning with `.pdf`, the container uses a batch script to do this operation.

[`bash file for the actual service behind the dotnet code`](https://github.com/ParsePort/DockerImages/blob/master/watchforfiles.sh)


### Bash for docker files
Linux services uses tools you would call via System.Diagnostics.Process, but to make it independent of OS, the communication to the processes are made via file transfer and a producer/consumer pattern. Therefore it is possible to resuse the Linux services for multiple purposes, without changing a lot in the code. All commands are handled in a bash script (if you are a bit familiar with your command line, terminal, bat, or even powershell, it will be relatively easy to follow). The idea is that each service has a base docker image, which handles all the installation of dependencies, OS version and so on. Then the docker image itself, will only run a bash script (.sh file), in this bash script, the main loop is a filewatcher (or folder watcher), each time a certain file is found and not produced, the service is called - it could be chrome headless via cli, where input format is html, and the output will be pdf, futhermore a .process file is created to make the bash script run in parallel (we use nohub for this).

[`sed`](https://www.gnu.org/software/sed/manual/sed.html) (**s**tream **ed**itor) is used for search/replace in files.

[`nohup`](https://linux.101hacks.com/unix/nohup-command/) (**no** **h**ang**up**, mening no hup signal is sent, which is the signal to tell that the user logged out of the process) is used to start the process in a background thread

Simple constructs in bash:
```
while true; do
  for f in $( find $dir -type f ); do
    input=$f
    if [[ ${f: -4} == ".pdf" ]]; then
```
Line 1 - a while loop to make sure the process nerver ends. Line 2 - a for-loop which lopps over all files (the f flag stands it is files only) in the folder defined in the declared variable `dir` loop to watch for certain files. Line 3 - assign the variable `f` to the variable `input`. When you want the value of a variable you add `$` in front. Line 4 a if-statement, where the last 4 charecters of the variable `f` is checked for being equal to `".pdf"`.


## Healthcheck service
Service to control that all environments (Production and Test) runs as expected. The service sends an Excel file for conversion, and expect a result within X minutes. The healthcheck service does also run a cronjob for controlling all public endpoints with respect to Mozilla Observatory (control of HTTPS headers).

OBS!: At the moment there is an issues with autehntication against production

Deployed to: https://parseport-healthcheck.azurewebsites.net/

## Test Case
The Test Case solution is build to act as an integration test towards any ParsePort environment, so you can have a large test set, which can be tested on Test, Production, even branch specific setups. The Test Case solution is deployed as an CDN hosted angular app with a backend deployed as an app service.

Deployed to: https://testcase.parseport.com/

## OCR services
If all fonts and all unicode chars are known, everything will be loaded from database, else it will start creating a pdf with unicode chars and unicode value, run this PDF through Azure cognitive services, and save the result to database and serve the result.
The OCR services caches the conversions, to speed up response time. The service does also caches the status, to avoid database interactions.

Deployed to: https://parseport-ocr.azurewebsites.net/

## Docker compose vs single docker container
Two different configuration modes are available for Azure web apps, single containers or compose. Single containers will be what you have in a normal Dockerfile, and the exposed port will be available at port 80 in the app service. Docker compose is like `docker-compose.yml`, and ressources can be linked.

To configure a new web app, it can be a bit cumbersome to test and setup, as the error messages are somehow hidden in Azure. But things to notice are:
1) Docker cannout run if you do not associate a fileshare or blob share to your web app

2) When assigning mounts, ${WEBAPP_STORAGE_HOME} are similar to `~` or the like.

3) The name of a "Path mapping" in configuration can be used directly in the docker compose, create a path mapping in settings, call it `filestorage_x` and use it in a mount like (in the Dockerfile or the docker-compose.yml):
```
volumes:
    filestorage_x:path/in/container
```

If you have a contianer which is slow for starting up, you can configure a larger limit by setting WEBSITES_CONTAINER_START_TIME_LIMIT as a configuration.

## Deployment
All web apps are set to automatically detect if a docker image is updated, and the web app will then download the newest version, and restart the web app with the newest version. In future, this can be changed, so images are built on changes in git, then pushed to azure with a tag, where latest would be deployed to development/test environments, and a certain tag is used for the one deployed to production. GitHub actions can be set up to do the build process, and a process for settting a release tag.

# Cosmos DB
For services in Azure which would like to use a MongoDB, a Cosmos DB is used. The Cosmos DB does not have a 1:1 map of all MongoDB features, specially indexing and shards are different. For heavy operations, please read the documentation for Cosmos, to optimize performance and minimize cost.
In the future it would be better to use a mLab solution hosted at Azure, so it is a real MongoDB, and the driver for C# is fully supported, and the developers will have the same setup as in production.

# Storage
For storage in Azure we use File shares, as blob storage for App Services are read-only. If you are running docker containers in App services, you have to mount a file share to the App service (the file share is used as a temporary location to download the docker image, so 1GB is more than enough).
