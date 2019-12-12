# parseport.guthub.io
A simple CMS for documentation of ParsePort XBRL engine / ParsePort API.

## How to run locally
To run the page localhost, just go to the root of the solution, and execute:

```
 bundle update && bundle exec jekyll serve
 ```

The Gemfile is responsible for the plugins you will need to run the solution

## Deploy the documentation
The `master` branch cannot be modified, as we use the `sources` to control markdown documents. The GitHub Action builds and deploy the site when you push to `sources`.
