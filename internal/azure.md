---
title: Services on Azure
#permalink: internal/
#has_children: true
#nav_order: 1
has_toc: false
---

# Container Registry
All docker images used by ParsePort are stored in the azure container registry: `parseport.azurecr.io`. The naming of the docker image reflects its purpose, and images named 'base' might not work individual, but only in collaboration with other images. Base images can minimize the build time and size of the resulting image, that uses the base image. Furthermore, base images can be used to control e.g. the OS version (if multiple images share a base).

# Cosmos DB
For services in Azure which would like to use a MongoDB, a Cosmos DB is used. The Cosmos DB does not have a 1:1 map of all MongoDB features, specially indexing and shards are different. For heavy operations, please read the documentation for Cosmos, to optimize performance and minimize cost.

# Storage
For storage in Azure we use File shares, as blob storage for App Services are read-only. If you are running docker containers in App services, you have to mount a file share to the App service.

# Web apps
TODO Create a drawing with services in relation to XBRL solution

## Linux services
The solution at https://github.com/ParsePort/ParsePort.XBRL.LinuxServices, contains the API and logic to combine a docker image for 3 different services. The C# code is constructed with a few configuration strings, to indicate which services that are available. The backend code contains logic to expose files generated in a docker container, in this setup the C# solution saves a set of files, which then are handled by a docker container, and when the new file is produced, the C# code can publish the result via the API.

* **pdf2html**

Service to convert PDF to HTML, the input file is a PDF, the output is HTML. The docker container is constructed to watch for files endning with `.pdf`, the container uses a batch script to do this operation. The docker container is running a linux, and everything is setup in the base image, and then a simple docker image exposing bash file.

* **iXBRLViewer**

Service to create a open source iXBRL viewer from any given taxonomy package. The input is a xHTML file and a set of taxonomy packages (zip files), the output is a HTML, including all CSS and Javascript. The docker container is constructed to watch for folders containing a xHTML with the same name of the folder, the container uses a batch script to do this operation. The docker container is running a linux, and everything is setup in the base image, and then a simple docker image exposing bash file.

* **html2png**

Service to convert html to png, the input file is a HTML, the output is png. The docker container is constructed to watch for files endning with `.html`, the container uses a batch script, and is running a headless chrome to do this operation. The docker container is running a linux, and everything is setup in the base image, and then a simple docker image exposing bash file.

### Bash for docker files
Linux services uses tools you would call via System.Diagnostics.Process, but to make it independent of OS, the communication to the processes are made via file transfer and a producer/consumer pattern. Therefore it is possible to resuse the Linux services for multiple purposes, without changing a lot in the code. All commands are handled in a bash script (if you are a bit familiar with your commnad line, bat, or even powershell, it will be relatively easy to follow). The idea is that each service has a base docker image, which handles all the installation of dependencies, OS version and so on. Then the docker image itself, will only run a bash script (.sh file), in this bash script, the main loop is a filewatcher (or folder watcher), each time a certain file is found and not produced, the service is called - it could be chrome headless via cli, where input format is html, and the output will be png, futhermore a .process file is created to make the bash script run in parallel (we use nohub for this).

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


## Health service
Not running proper due to timing constraints - runs locally.

## Test Cases
Not running due to an issue with the docker container for this solution!


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


## Deployment
All web apps are set to automatically detect if a docker image is updated, and the web app will then download the newest version, and restart the web app with the newest version. In future, this can be changed, so images are built on changes in git, then pushed to azure with a tag, where latest would be deployed to test environments, and a tag is used for the one deployed to production. Github actions can be set up to do the build process, and a process for settting a release tag.
