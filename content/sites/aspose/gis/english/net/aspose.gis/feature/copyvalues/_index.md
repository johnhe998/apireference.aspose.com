---
title: Feature.CopyValues
second_title: Aspose.GIS for .NET API Reference
description: Feature method. Copies values of attributes from another feature.
type: docs
weight: 20
url: /net/aspose.gis/feature/copyvalues/
---
## Feature.CopyValues method

Copies values of attributes from another feature.

```csharp
public void CopyValues(Feature inputFeature)
```

| Parameter | Type | Description |
| --- | --- | --- |
| inputFeature | Feature | The feature to copy values from. |

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentNullException | The argument is `null`. |
| ArgumentException | The attribute with this name does not exist in this layer. |
| InvalidOperationException | The attribute is not locked. |
| InvalidOperationException | Input value is null an the attribute in this feature cannot be null. |
| [GisException](../../gisexception/) | An attribute has same name but different data types in the features. |

### Remarks

This method only copies attributes with matching names.

### See Also

* class [Feature](../)
* namespace [Aspose.Gis](../../feature/)
* assembly [Aspose.GIS](../../../)


