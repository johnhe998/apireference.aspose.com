---
title: RasterLayer.GetSpatialPoint
second_title: Aspose.GIS for .NET API Reference
description: RasterLayer method. Converts the specified column and row to the spatial coordinate.
type: docs
weight: 150
url: /net/aspose.gis.raster/rasterlayer/getspatialpoint/
---
## RasterLayer.GetSpatialPoint method

Converts the specified column and row to the spatial coordinate.

```csharp
public IPoint GetSpatialPoint(int cellX, int cellY)
```

| Parameter | Type | Description |
| --- | --- | --- |
| cellX | Int32 | The value for column (x-coordinate). Numbering starts at 0. |
| cellY | Int32 | The value for row (y-coordinate). Numbering starts at 0. |

### Return Value

Returns the x-coordinate of upper left corner given a column and row.

### Remarks

If either parameter is passed out of range of the respective dimension of the raster, it will return coordinates outside of the raster assuming the raster's grid is applicable outside the raster's bounds.

### See Also

* interface [IPoint](../../../aspose.gis.geometries/ipoint/)
* class [RasterLayer](../)
* namespace [Aspose.Gis.Raster](../../rasterlayer/)
* assembly [Aspose.GIS](../../../)


