---
title: ParsePort JSON format
permalink: /services/conversion/json
parent: Services
nav_order: 1
has_toc: false
---
# ParsePort JSON format
For our partners, we offer API integration, where we can recieve the input data in either Excel or JSON. For Excel, we help you with tagging of your own Excel, and then it is just a matter of uploading. For JSON integration we have the following structure for the input data:

__TODO__: *We need more on the overall structure for the input json!!*

```csharp
namespace ParsePort.XBRL.Conversion.Json
{
    public class ItemValue
    {
        /// <summary>
        /// The presentational value of the value.
        /// (1,234) kr.
        /// -1,234
        /// For textual elements, it is possible to reference other values by using @@CorrelationId@@ where CorrelationId is the CorrelationId of the value being referenced.
        /// </summary>
        public string Value { get; set; }

        /// <summary>
        /// Used to indicate that the value is negative even though the string value is positive.
        /// </summary>
        public bool? IsNegative { get; set; }

        /// <summary>
        /// Can be used to correlate a value in the response with this value.
        /// </summary>
        public string CorrelationId { get; set; }

        /// <summary>
        /// Allows values from different items to be grouped together.
        /// Usually this would be to indicate that values share the same properties.
        /// </summary>
        public string GroupId { get; set; }

        /// <summary>
        /// An Excel style format string indicating which format the value is in.
        /// Include link to supported ixbrl formats.
        /// </summary>
        public string FormatString { get; set; }

        /// <summary>
        /// Copy from Period
        /// </summary>
        public int? Scale { get; set; }

        /// <summary>
        /// Language of the value.
        /// </summary>
        public string Language { get; set; }

        /// <summary>
        /// Sets the style name to use for values
        /// </summary>
        public string StyleName { get; set; }
    }
}

```

__TODO__: *We need more here - full example where we remove parts of the input json!!*
Column and Row is used for ordering of the elements - we use the same termology as for our Excel import. All settings in the JSON can be customized per element, e.g. scale, which is set as 6 per element, but could be set as an overall settting, and changed where appropiate. Scale is used for monitary values, so you can indicate values in millions without writing out zeros.
```json
{
  id: "YOUR-OWN-UNIQUE-KEY-FOR-THIS-TABLE",
  label: "Income statement",
  columns: [
    {
      column: 10,
      label: "2018",
      processLabel: false,
      rows: [
        {
          id: "YOUR-OWN-UNIQUE-KEY-FOR-THIS-LABEL",
          isNegative: false,
          itemType: "element",
          label: "Revenue",
          row: 7,
          scale: 6,
          style: "standard",
          value: "234,234"
        },
        {
          id: "YOUR-OWN-UNIQUE-KEY-FOR-THIS-LABEL",
          isNegative: false,
          itemType: "element",
          label: "Cost of services",
          row: 8,
          scale: 6,
          style: "standard",
          value: "123,123"
        },
        ...
      ],
      column: 11,
      label: "2017",
      processLabel: false,
      rows: [
        {
          id: "YOUR-OWN-UNIQUE-KEY-FOR-THIS-LABEL",
          isNegative: false,
          itemType: "element",
          label: "Revenue",
          row: 7,
          scale: 6,
          style: "standard",
          value: "22,222"
        },
        {
          id: "YOUR-OWN-UNIQUE-KEY-FOR-THIS-LABEL",
          isNegative: false,
          itemType: "element",
          label: "Cost of services",
          row: 8,
          scale: 6,
          style: "standard",
          value: "11,111"
        },
        ...
        ]
    }
  ]
}
```
