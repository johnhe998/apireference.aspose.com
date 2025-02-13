---
title: ShapeCollection.AddIcons
second_title: Aspose.Cells for .NET API Reference
description: ShapeCollection method. Adds svg image
type: docs
url: /net/aspose.cells.drawing/shapecollection/addicons/
---
## ShapeCollection.AddIcons method

Adds svg image.

```csharp
public Picture AddIcons(int upperLeftRow, int top, int upperLeftColumn, int left, int height, 
    int width, byte[] imageByteData, byte[] compatibleImageData)
```

| Parameter | Type | Description |
| --- | --- | --- |
| upperLeftRow | Int32 | Upper left row index. |
| top | Int32 | Represents the vertical offset of shape from its left row, in unit of pixel. |
| upperLeftColumn | Int32 | Upper left column index. |
| left | Int32 | The horizontal offset of shape from its left column, in unit of pixel. |
| height | Int32 | The height of shape, in unit of pixel. |
| width | Int32 | The width of shape, in unit of pixel. |
| imageByteData | Byte[] | The image byte data. |
| compatibleImageData | Byte[] | Converted image data from svg in order to be compatible with Excel 2016 or lower versions. |

### Examples

```csharp

[C#]
//add icon
using (FileStream fs = new FileStream("icon.svg", FileMode.Open))
{
    int len = (int)fs.Length;
    byte[] imageData = new byte[len];
    fs.Read(imageData, 0, len);
    Picture picture = shapes.AddSvg(4, 0, 5, 0, -1, -1, imageData, null);
}
```

### See Also

* class [Picture](../../picture/)
* class [ShapeCollection](../)
* namespace [Aspose.Cells.Drawing](../../../aspose.cells.drawing/)
* assembly [Aspose.Cells](../../../)


