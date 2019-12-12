---
title: JSON format for ParsePort API
permalink: services/api/json
parent: Services
nav_order: 1
has_toc: false
---
# ParsePort JSON format
The ParsePort API accepts multiple formats, and the most common format is Excel. If you use Excel, ParsePort will help you to setup your Excel with ParsePort simplified tagging. if you are a partner, you can use the API, where the format can be either Excel with simplified tagging or you can use our JSON format. For JSON integration we have the following structure for the input data (explanations after the JSON example):

**TODO** Add examples for GAAP, EBA, EIOPA and ESEF eg with accordion

```json
{
  "version": 1.0,
  "configuration": {
    "taxonomy": "ESEF 20170331",
    "language": "en",
    "entrypoint": "All",
    "taxonomyExtension": {
      "baseUri": "https://www.CompanyX.com/taxonomy/2018-12-31",
      "prefix": "CX",
      "name": "CX_20181231"
    }
  },
  "containers": [
    {
      "id": "General data label",
      "label": "General data label",
      "columns": [
        {
          "column": 7,
          "label": "General data consolidated current year",
          "processLabel": true,
          "rows": [
            {
              "id": "general-data-esef__7__11",
              "itemType": "element",
              "label": "Identifier scheme",
              "row": 11,
              "value": "http://standards.iso.org/iso/17442"
            },
            {
              "id": "general-data-esef__7__13",
              "itemType": "element",
              "label": "Entrypoint",
              "row": 13,
              "value": "All"
            },
            {
              "id": "general-data-esef__7__14",
              "itemType": "element",
              "label": "Currency code",
              "row": 14,
              "value": "EUR"
            },
            {
              "id": "general-data-esef__7__17",
              "itemType": "element",
              "label": "Name of reporting entity or other means of identification",
              "row": 17,
              "value": "CompanyX"
            },
            {
              "id": "general-data-esef__7__21",
              "itemType": "element",
              "label": "Country of incorporation",
              "row": 21,
              "value": "Denmark"
            },
            {
              "id": "general-data-esef__7__29",
              "itemType": "element",
              "label": "Date of start of reporting period",
              "row": 29,
              "value": "2018-01-01"
            },
            {
              "id": "general-data-esef__7__30",
              "itemType": "element",
              "label": "Date of end of reporting period",
              "row": 30,
              "value": "2018-12-31"
            },
            {
              "id": "general-data-esef__7__31",
              "itemType": "element",
              "label": "Date of start of previous reporting period",
              "row": 31,
              "value": "2017-01-01"
            },
            {
              "id": "general-data-esef__7__32",
              "itemType": "element",
              "label": "Date of end of previous reporting period",
              "row": 32,
              "value": "2017-12-31"
            },
            {
              "id": "general-data-esef__7__36",
              "itemType": "element",
              "label": "ID number of reporting entity",
              "row": 36,
              "value": "223300BXXJITVLKVYY11"
            }
          ]
        }
      ]
    },
    {
      "label": "Income statement",
      "columns": [
        {
          "column": 10,
          "processLabel": false,
          "rows": [
            {
              "id": "income-statement__10__7",
              "isNegative": false,
              "itemType": "element",
              "label": "Sales",
              "row": 7,
              "scale": 6,
              "style": "standard",
              "value": "3,156.1"
            },
            {
              "id": "income-statement__10__9",
              "isNegative": false,
              "itemType": "element",
              "label": "Other operating income",
              "row": 9,
              "scale": 6,
              "style": "standard",
              "value": "6.3"
            },
            {
              "id": "income-statement__10__10",
              "isNegative": true,
              "itemType": "element",
              "label": "Materials, supplies and subcontracting",
              "row": 10,
              "scale": 6,
              "value": "-1,371.9"
            },
            {
              "id": "income-statement__10__11",
              "isNegative": true,
              "itemType": "element",
              "label": "Personnel cost",
              "row": 11,
              "scale": 6,
              "value": "-1,006.5"
            },
            {
              "id": "income-statement__10__12",
              "isNegative": true,
              "itemType": "element",
              "label": "Depreciation and impairments",
              "row": 12,
              "scale": 6,
              "value": "-119.9"
            },
            {
              "id": "income-statement__10__13",
              "isNegative": true,
              "itemType": "element",
              "label": "Other operating expenses",
              "row": 13,
              "scale": 6,
              "value": "-498.0"
            },
            {
              "calculations": [
                {
                  "weight": "1",
                  "valueId": "income-statement__10__7"
                },
                {
                  "weight": "1",
                  "valueId": "income-statement__10__9"
                },
                {
                  "weight": "1",
                  "valueId": "income-statement__10__10"
                },
                {
                  "weight": "1",
                  "valueId": "income-statement__10__11"
                },
                {
                  "weight": "1",
                  "valueId": "income-statement__10__12"
                },
                {
                  "weight": "1",
                  "valueId": "income-statement__10__13"
                }
              ],
              "id": "income-statement__10__15",
              "isNegative": false,
              "itemType": "element",
              "label": "Operating profit",
              "row": 15,
              "scale": 6,
              "value": "166.1"
            },
            {
              "id": "income-statement__10__17",
              "isNegative": false,
              "itemType": "element",
              "label": "Share of associates' and joint ventures' result",
              "row": 17,
              "scale": 6,
              "value": "4.0"
            },
            ...
          ],
          "periodId": "CY",
          "scale": 6
        },
        {
          "column": 12,
          "processLabel": false,
          "rows": [
            {
              "id": "income-statement__12__7",
              "isNegative": false,
              "itemType": "element",
              "label": "Sales",
              "row": 7,
              "scale": 6,
              "style": "standard",
              "value": "3,137.2"
            },
            {
              "id": "income-statement__12__9",
              "isNegative": false,
              "itemType": "element",
              "label": "Other operating income",
              "row": 9,
              "scale": 6,
              "style": "standard",
              "value": "227.2"
            },
            ...
          ],
          "periodId": "LY",
          "scale": 6
        }
      ]
    },
    {
      "label": "Comprehensive income",
      "columns": [
        {
          "column": 10,
          "processLabel": false,
          "rows": [
            {
              "id": "comprehensive-income__10__7",
              "isNegative": false,
              "itemType": "element",
              "label": "Profit for the period",
              "row": 7,
              "scale": 6,
              "style": "standard",
              "value": "98.3"
            },
            {
              "id": "comprehensive-income__10__9",
              "isNegative": true,
              "itemType": "element",
              "label": "Cash flow hedges",
              "row": 9,
              "scale": 6,
              "style": "standard",
              "value": "-13.4"
            },
            ...
          ]
        },
      ]
    }
  ]
}
```

Overall the JSON format follows the structure from Excel, where you would have a sheet with settings, and then a set of sheets (here `container`´s) with a table format (`rows` and `columns`).

* `container` : has an `id` and a set of `columns`.
  - `General data label` : a container to specify general settings / data such as reporting company, start and end dates for the reporting period.
* `columns` / `rows` : provides an ordering of the elements. Column and Row is used for ordering of the elements. `columns` and `rows` have the same terminology as for Excel.

* `configuration` : used to set the scope of the conversion, overall setting for `language` in ISO 639-1 format, sets the taxonomy, for the example here it is ESEF (avaliable taxonomies can be found [here](https://xbrlapi.parseport.com/api/taxonomies))
* `taxonomyExtension` :
  - `baseUri` : sets the namespace for the custom part of the taxonomy, standard naming is: company website + /taxonomy/ + period end date e.g. "https://www.CompanyX.com/taxonomy/2018-12-31"
  - `prefix` : used for setting a prefix on the XBRL elements in the iXBRL document.
  - `name` : used for the filename of the resulting iXBRL package (available  as a zip file).

All settings in the JSON can be customized per element, e.g. scale, which is set as 6 per element. Settings are inherited, so you can specific general settings like `language` as an overall setting, and then change it at certain elements.

* `id` : unique identifier for the value and label. You can use this, if you would like to do postprocessing of the iXBRL output or to reference values in textual elements.
* `label` : used to map the value with the correct XBRL element in the given taxonomy.
* `value` : represents the actual content, which should be converted to a XBRL element in the XHTML. The content should be written as how you would present the content e.g. (1,234) or -1,234. For textual elements, it is possible to reference other values by using @@CorrelationId@@ where CorrelationId is `id` of the value being referenced.
* `itemType` : can take one of the following formats: `element` (default) / `content` / `footnote`
* `calculations` : used to represent the narrower/wider specification in ESEF. Calculations consists of two parts, the `weight` which can be `1` for addition or `-1` for subtraction, `valueId` which is a reference to a `row` value.
* `scale` : is used for monetary values, so you can indicate values in millions without writing out 6 zeros. 3 indicates that the values are in thousands. 6 indicates that the values are in millions.
* `isNegative` : indicates whether the value should be negative or not, even if the value is written as a positive number.
* `style` : indicates a class to add for the XBRL element in the XHTML output.
* `processLabel` : indicates whether we should make a lookup of the label in the database, for tables with header and row label, the `processLabel` can be used to lookup both labels.
* `language` : the language of the `value`/`label` in ISO 639-1 format.
* `periodId` : reference to a representation of the period for the given values. The reference can be to standard periods defined by ParsePort (`CY` current year and `LY` last year), or to periods defined in `General data`.
