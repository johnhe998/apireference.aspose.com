---
title: TopoJsonOptions.DefaultObjectName
second_title: Aspose.GIS for .NET API Reference
description: TopoJsonOptions property. Name of the object where features are put by default.
type: docs
weight: 20
url: /net/aspose.gis.formats.topojson/topojsonoptions/defaultobjectname/
---
## TopoJsonOptions.DefaultObjectName property

Name of the object where features are put by default.

```csharp
public string DefaultObjectName { get; set; }
```

### Remarks

This is writing option - it does not affect reading. TopoJSON may contain any number of named objects. Every such object can contain multiple features. In order to specify in which object to put your feature, use [`ObjectNameAttribute`](../objectnameattribute/) property. If attribute with name [`ObjectNameAttribute`](../objectnameattribute/) is `null` or unset for some feature, this feature is added to object with the name `DefaultObjectName`. If attribute with name [`ObjectNameAttribute`](../objectnameattribute/) is not present in [`Attributes`](../../../aspose.gis/vectorlayer/attributes/) collection, all features are put into object with name [`ObjectNameAttribute`](../objectnameattribute/). Default value is "unnamed".

### See Also

* class [TopoJsonOptions](../)
* namespace [Aspose.Gis.Formats.TopoJson](../../topojsonoptions/)
* assembly [Aspose.GIS](../../../)


