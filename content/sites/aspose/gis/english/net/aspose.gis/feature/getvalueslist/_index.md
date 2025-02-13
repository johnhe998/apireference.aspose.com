---
title: Feature.GetValuesList
second_title: Aspose.GIS for .NET API Reference
description: Feature method. Gets the values of an attributes sequence as a list.
type: docs
weight: 70
url: /net/aspose.gis/feature/getvalueslist/
---
## Feature.GetValuesList&lt;T&gt; method

Gets the values of an attributes sequence as a list.

```csharp
public List<T> GetValuesList<T>(string attributeName, string separator)
```

| Parameter | Description |
| --- | --- |
| T | Desired type for the values. |
| attributeName | Name of the attribute. |
| separator | A string which is used to separate attribute name and index value of sequence. |

### Return Value

List of values of the attributes which names different by sequence index value.

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentNullException | The attribute name is `null`. |
| ArgumentException | The attribute with this name does not exist in this layer. |
| InvalidOperationException | The attribute is not locked. |
| InvalidOperationException | The value of this attribute is not set for this feature. |
| InvalidCastException | The requested type does not implement IConvertible. |
| InvalidCastException | Value of the attribute is `null`, but the requested type is a value type. |
| FormatException | Conversion failed because the value is in incorrect format. |
| OverflowException | Conversion failed because of overflow. |

### Remarks

This uses [`GetValue`](../getvalue/) to get single value. So, this method converts the value automatically to the type requested in the generic type parameter.  If attribute with index 0 will not be found it will generate ArgumentException.

### See Also

* class [Feature](../)
* namespace [Aspose.Gis](../../feature/)
* assembly [Aspose.GIS](../../../)


