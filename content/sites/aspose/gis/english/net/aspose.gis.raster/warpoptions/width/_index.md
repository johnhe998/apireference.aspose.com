---
title: WarpOptions.Width
second_title: Aspose.GIS for .NET API Reference
description: WarpOptions property. Specifies output raster width in pixels and columns. If the value is set to 0 the width is automatically computed. The default value is 0.
type: docs
weight: 80
url: /net/aspose.gis.raster/warpoptions/width/
---
## WarpOptions.Width property

Specifies output raster width in pixels and columns. If the value is set to 0, the width is automatically computed. The default value is "0".

```csharp
public int Width { get; set; }
```

### Remarks

If the width is set to 0, the value will be taken from the original width or computed from [`CellWidth`](../cellwidth/). Note that `Width` cannot be used with [`CellWidth`](../cellwidth/).

### See Also

* class [WarpOptions](../)
* namespace [Aspose.Gis.Raster](../../warpoptions/)
* assembly [Aspose.GIS](../../../)


