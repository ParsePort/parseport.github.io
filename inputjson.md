---
title: ParsePort JSON format
permalink: /services/conversion/json
parent: Services
nav_order: 1
has_toc: false
---


```csharp
namespace ParsePort.XBRL.Conversion.Json
{
    public class ItemValue
    {
        /// <summary>
        /// Indicates which period the value belongs to.
        /// It must be a valid periodId.
        /// </summary>
        public string PeriodId { get; set; }

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
        /// Copy from Period
        /// </summary>
        public int? Decimals { get; set; }
        /// <summary>
        /// Copy from Period
        /// </summary>
        public string Precision { get; set; }

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
Example
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
