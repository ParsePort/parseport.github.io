---
title: Services
permalink: /services/
---

## API structure
For all services we have the following endpoints:
```
POST api/{service}
GET  api/{service}/{id}/status
GET  api/{service}/{id}
```
### POST api/{service}
To start a service, you have to POST the required files to the service, you will then receive an _id_, to get the status of the service and to download the result.

### GET  api/{service}/{id}/status
For services where the processing contains multiple steps, you can get the progression at the endpoint. The endpoint returns JSON, with a boolean value indication if the process is completed.

### GET  api/{service}/{id}
This endpoint let you download the result of the process done by the service, it could be a PDF, a HTML document or the like.
