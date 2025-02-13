---
title: WarpOptions.CellWidth
second_title: Aspose.GIS for .NET API Reference
description: WarpOptions property. Specifies a new width of the raster cell in target georeferenced units. If the value is set to 0 the CellWidth is automatically computed. The default value is 0.
type: docs
weight: 30
url: /net/aspose.gis.raster/warpoptions/cellwidth/
---
## WarpOptions.CellWidth property

Specifies a new width of the raster cell (in target georeferenced units). If the value is set to 0, the `CellWidth` is automatically computed. The default value is "0".

```csharp
public double CellWidth { get; set; }
```

### Remarks

If the cell width is set to 0, the value will be taken from the original cell width or computed from [`Width`](../width/). Note that `CellWidth` cannot be used with [`Width`](../width/).

### See Also

* class [WarpOptions](../)
* namespace [Aspose.Gis.Raster](../../warpoptions/)
* assembly [Aspose.GIS](../../../)


