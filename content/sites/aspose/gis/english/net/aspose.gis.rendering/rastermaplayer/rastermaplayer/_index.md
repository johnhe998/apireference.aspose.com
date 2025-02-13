---
title: RasterMapLayer.RasterMapLayer
second_title: Aspose.GIS for .NET API Reference
description: RasterMapLayer constructor. Creates new instance.
type: docs
weight: 10
url: /net/aspose.gis.rendering/rastermaplayer/rastermaplayer/
---
## RasterMapLayer constructor

Creates new instance.

```csharp
public RasterMapLayer(RasterLayer layer, RasterColorizer colorizer = null, bool keepOpen = false)
```

| Parameter | Type | Description |
| --- | --- | --- |
| layer | RasterLayer | Raster layer. |
| colorizer | RasterColorizer | Symbolizer to use to render layer. If `null`, default colorizer will be used. |
| keepOpen | Boolean | `true` to leave the layer open after the [`VectorMapLayer`](../../vectormaplayer/) object is disposed; otherwise, `false`. |

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentNullException | Layer is `null`. |

### See Also

* class [RasterLayer](../../../aspose.gis.raster/rasterlayer/)
* class [RasterColorizer](../../../aspose.gis.rendering.colorizers/rastercolorizer/)
* class [RasterMapLayer](../)
* namespace [Aspose.Gis.Rendering](../../rastermaplayer/)
* assembly [Aspose.GIS](../../../)


