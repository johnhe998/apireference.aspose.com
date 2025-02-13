---
title: TopoJsonDriver.SupportsSpatialReferenceSystem
second_title: Aspose.GIS for .NET API Reference
description: TopoJsonDriver method. Determines whether specified spatial reference system is supported by the driver.
type: docs
weight: 60
url: /net/aspose.gis.formats.topojson/topojsondriver/supportsspatialreferencesystem/
---
## TopoJsonDriver.SupportsSpatialReferenceSystem method

Determines, whether specified spatial reference system is supported by the driver.

```csharp
public override bool SupportsSpatialReferenceSystem(SpatialReferenceSystem spatialReferenceSystem)
```

| Parameter | Type | Description |
| --- | --- | --- |
| spatialReferenceSystem | SpatialReferenceSystem | Spatial reference system. |

### Return Value

Boolean value, indicating whether specified spatial reference system is supported by the driver.

### Remarks

For TopoJSON, the only supported spatial reference system is 'null', since there is no way to store spatial reference system information in TopoJSON file and TopoJSON specification does not specify what is the spatial reference system of geometries in TopoJSON file.

### See Also

* class [SpatialReferenceSystem](../../../aspose.gis.spatialreferencing/spatialreferencesystem/)
* class [TopoJsonDriver](../)
* namespace [Aspose.Gis.Formats.TopoJson](../../topojsondriver/)
* assembly [Aspose.GIS](../../../)


