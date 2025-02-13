---
title: Feature.GetValues
second_title: Aspose.GIS for .NET API Reference
description: Feature method. Returns the values for all the attributes in an array.
type: docs
weight: 50
url: /net/aspose.gis/feature/getvalues/
---
## Feature.GetValues method

Returns the values for all the attributes in an array.

```csharp
public int GetValues(object[] values, object defaultValue = null)
```

| Parameter | Type | Description |
| --- | --- | --- |
| values | Object[] | The array into which to copy the attributes values. |
| defaultValue | Object | The value to return if the attribute value is missing (unset). Default value is `null`. Consider to use 'DBNull.Value' for separating 'unset' and '`null`' values. |

### Return Value

A number of attributes copied.

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentNullException | The argument is `null`. |
| InvalidOperationException | The attribute is not locked. |

### Remarks

The values attributes of the feature are copied into the values array that is passed as a parameter. For attributes with unset value, the specified 'unsetValue' parameter is returned.  The length of the values array does not need to match the number of attributes in the feature. If the array length is greater than the number of attributes, all of the attribute values are copied into the array; if it is less, only the array length number of attribute values is copied into the array, starting at the attribute value with ordinal 0.

### See Also

* class [Feature](../)
* namespace [Aspose.Gis](../../feature/)
* assembly [Aspose.GIS](../../../)


