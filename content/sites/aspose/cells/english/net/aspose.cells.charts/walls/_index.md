---
title: Class Walls
second_title: Aspose.Cells for .NET API Reference
description: Aspose.Cells.Charts.Walls class. Encapsulates the object that represents the walls of a 3D chart
type: docs
url: /net/aspose.cells.charts/walls/
---
## Walls class

Encapsulates the object that represents the walls of a 3-D chart.

```csharp
public class Walls : Floor
```

## Properties

| Name | Description |
| --- | --- |
| [BackgroundColor](../../aspose.cells.drawing/area/backgroundcolor/) { get; set; } | Gets or sets the background Color of the [`Area`](../../aspose.cells.drawing/area/).(Inherited from [`Area`](../../aspose.cells.drawing/area/).) |
| [Border](../../aspose.cells.charts/floor/border/) { get; set; } | Gets or sets the border [`Line`](../../aspose.cells.drawing/line/).(Inherited from [`Floor`](../floor/).) |
| [CenterX](../../aspose.cells.charts/walls/centerx/) { get; } | Gets the x coordinate of the left-bottom corner of Wall center in units of 1/4000 of chart's width after calls Chart.Calculate() method. |
| [CenterXPx](../../aspose.cells.charts/walls/centerxpx/) { get; } | Gets the x coordinate of the left-bottom corner of Wall center in units of pixels after calls Chart.Calculate() method. |
| [CenterY](../../aspose.cells.charts/walls/centery/) { get; } | Gets the y coordinate of the left-bottom corner of Wall center in units of 1/4000 of chart's height after calls Chart.Calculate() method. |
| [CenterYPx](../../aspose.cells.charts/walls/centerypx/) { get; } | Gets the y coordinate of the left-bottom corner of Wall center in units of pixels after calls Chart.Calculate() method. |
| [Depth](../../aspose.cells.charts/walls/depth/) { get; } | Gets the depth front to back in units of 1/4000 of chart's width after calls Chart.Calculate() method. |
| [DepthPx](../../aspose.cells.charts/walls/depthpx/) { get; } | Gets the depth front to back in units of pixels after calls Chart.Calculate() method. |
| [FillFormat](../../aspose.cells.drawing/area/fillformat/) { get; } | Represents a  object that contains fill formatting properties for the specified chart or shape.(Inherited from [`Area`](../../aspose.cells.drawing/area/).) |
| [ForegroundColor](../../aspose.cells.drawing/area/foregroundcolor/) { get; set; } | Gets or sets the foreground Color.(Inherited from [`Area`](../../aspose.cells.drawing/area/).) |
| [Formatting](../../aspose.cells.drawing/area/formatting/) { get; set; } | Represents the formatting of the area.(Inherited from [`Area`](../../aspose.cells.drawing/area/).) |
| [Height](../../aspose.cells.charts/walls/height/) { get; } | Gets the height of top to bottom in units of 1/4000 of chart's height after calls Chart.Calculate() method. |
| [HeightPx](../../aspose.cells.charts/walls/heightpx/) { get; } | Gets the height of top to bottom in units of pixels after calls Chart.Calculate() method. |
| [InvertIfNegative](../../aspose.cells.drawing/area/invertifnegative/) { get; set; } | If the property is true and the value of chart point is a negative number, the foreground color and background color will be exchanged.(Inherited from [`Area`](../../aspose.cells.drawing/area/).) |
| [Transparency](../../aspose.cells.drawing/area/transparency/) { get; set; } | Returns or sets the degree of transparency of the area as a value from 0.0 (opaque) through 1.0 (clear).(Inherited from [`Area`](../../aspose.cells.drawing/area/).) |
| [Width](../../aspose.cells.charts/walls/width/) { get; } | Gets the width of left to right in units of 1/4000 of chart's width after calls Chart.Calculate() method. |
| [WidthPx](../../aspose.cells.charts/walls/widthpx/) { get; } | Gets the width of left to right in units of pixels after calls Chart.Calculate() method. |

## Methods

| Name | Description |
| --- | --- |
| [GetCubePointCount](../../aspose.cells.charts/walls/getcubepointcount/)() | Gets the number of cube points after calls Chart.Calculate() method. |
| [GetCubePointXPx](../../aspose.cells.charts/walls/getcubepointxpx/)(int) | Gets x-coordinate of the apex point of walls cube after calls Chart.Calculate() method. The number of apex points of walls cube is eight |
| [GetCubePointYPx](../../aspose.cells.charts/walls/getcubepointypx/)(int) | Gets y-coordinate of the apex point of walls cube after calls Chart.Calculate() method. The number of apex points of walls cube is eight. |

### See Also

* class [Floor](../floor/)
* namespace [Aspose.Cells.Charts](../../aspose.cells.charts/)
* assembly [Aspose.Cells](../../)


