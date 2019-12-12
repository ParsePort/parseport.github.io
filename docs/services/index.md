---
title: Services
permalink: services/
has_children: true
nav_order: 1
has_toc: false
---
# Services
Overall the [ParsePort API](https://xbrlapi.parseport.com) has four services to offer, and then one service for providing inputs to the other four services. The four services can be used independently or in steps starting with: **[Extract]** - the service for disassamble your financhial data, this can be from JSON, Excel, CSV or even Word. Then **[Conversion]** which adds meta data to your finansial data and translate your values into XBRL. **[Validation]** validates the XBRL against the given taxonomy, to make sure that the correct rules are followed. The last step is to **[Render]** the validated XBRL, and transform it to either XHTML or JSON, which then can be used to report your data to your local authorities. **[Taxonomies]** provides a set of taxonomies support by ParsePort. Furthermore, **[Taxonomies]** provides generel setttings you can use in your input to ParsePort API.

In the following you can read about the used structure for the ParsePort API. If you would like to use the API, you can find the documentation for the input format, please visit [JSON input for API](inputjson.md).

## API structure
For all services we have the following endpoints:
```
POST api/{service}
GET  api/{service}/{id}/status
GET  api/{service}/{id}/errors
GET  api/{service}/{id}
```
### POST api/{service}
To start a service, you have to POST the required files to the service, you will then receive a guid _id_, to get the status of the service and to download the result.

### GET  api/{service}/{id}/status
For services where the processing contains multiple steps, you can get the progression at the endpoint. The endpoint returns JSON, with a boolean value indication if the process is completed.

### GET  api/{service}/{id}/errors
If an error is present in e.g. a conversion of Excel to iXBRL, you will get the validation errors here.

### GET  api/{service}/{id}/report
This endpoint let you download the result of the process done by the service, it could be a PDF, a HTML document or the like.

## Available services in ParsePort API
Here you can find the entry points for [https://xbrlapi.parseport.com](https://xbrlapi.parseport.com), and a short summary. Please visit [https://xbrlapi.parseport.com](https://xbrlapi.parseport.com) for more information.

<div>
  <ul>
  {% for param in site.data.swagger.paths %}
    <li>
    {% if param contains 'get' %}
      <h3>GET {{ param.path }}</h3>
    {% endif %}
    {% if param contains 'put' %}
      <h3>PUT {{ param.path }}</h3>
    {% endif %}
    {% if param contains 'post' %}
      <h3>POST {{ param.path }}</h3>
    {% endif %}
    {% if param contains 'delete' %}
      <h3>DELETE {{ param.path }}</h3>
    {% endif %}
      <p>{{ param.verbs.first.summary }}</p>
    </li>
  {% endfor %}
  </ul>
</div>
