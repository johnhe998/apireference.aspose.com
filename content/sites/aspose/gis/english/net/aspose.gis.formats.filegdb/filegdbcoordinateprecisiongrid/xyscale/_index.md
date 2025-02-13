---
title: FileGdbCoordinatePrecisionGrid.XYScale
second_title: Aspose.GIS for .NET API Reference
description: FileGdbCoordinatePrecisionGrid property. Gets or sets the scale of X and Y coordinates. If set to null the default is used.
type: docs
weight: 60
url: /net/aspose.gis.formats.filegdb/filegdbcoordinateprecisiongrid/xyscale/
---
## FileGdbCoordinatePrecisionGrid.XYScale property

Gets or sets the scale of X and Y coordinates. If set to `null` the default is used.

```csharp
public double? XYScale { get; set; }
```

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentOutOfRangeException | Argument is not positive. |

### Remarks

Default value is `1e9` for [`VectorLayer`](../../../aspose.gis/vectorlayer/) with geographic [`SpatialReferenceSystem`](../../../aspose.gis.spatialreferencing/spatialreferencesystem/) and `XYScale = 1 / XYTolerance * 10` for [`VectorLayer`](../../../aspose.gis/vectorlayer/) with projected [`SpatialReferenceSystem`](../../../aspose.gis.spatialreferencing/spatialreferencesystem/).

### See Also

* class [FileGdbCoordinatePrecisionGrid](../)
* namespace [Aspose.Gis.Formats.FileGdb](../../filegdbcoordinateprecisiongrid/)
* assembly [Aspose.GIS](../../../)


