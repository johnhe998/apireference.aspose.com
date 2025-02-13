---
title: NumericFormat.General
second_title: Aspose.GIS for .NET API Reference
description: NumericFormat method. Converts a number to the more compact of either fixedpoint or scientific notation depending on the type of the number and whether a precision specifier is present. Recommended to use.
type: docs
weight: 30
url: /net/aspose.gis/numericformat/general/
---
## NumericFormat.General method

Converts a number to the more compact of either fixed-point or scientific notation, depending on the type of the number and whether a precision specifier is present. Recommended to use.

```csharp
public static NumericFormat General(int precision = 0)
```

| Parameter | Type | Description |
| --- | --- | --- |
| precision | Int32 | The precision defines the maximum number of significant digits that can appear in the result string. If the precision is zero, the value "15" is used. The maximum available precision is "17". |

### Return Value

The General Format Specifier.

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentOutOfRangeException | Number of significant digits is less then 0 or more than 17. |

### Remarks

Internally code is generating number strings for WKT via: coordinate.ToString("G", CultureInfo.InvariantCulture).

### See Also

* class [NumericFormat](../)
* namespace [Aspose.Gis](../../numericformat/)
* assembly [Aspose.GIS](../../../)


