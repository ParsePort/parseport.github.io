# parseport.guthub.io
A simple CMS for documentation of ParsePort XBRL engine / ParsePort API.

## Why _site is commited to this repo
We are using a plugin for integration towards swagger, therefore we need to build the page at localhost and deploy the full solution. It is not optimal, but it is a necessarity for having the full documentation.

```
 bundle update && bundle exec jekyll build
 git add . && git commit -m "documentated updated with ..."
 git push
 ```
