---
title: GraphicsQualityOptions.UseTileFlipMode
second_title: Aspose.Words für .NET-API-Referenz
description: GraphicsQualityOptions eigendom. Ruft ein Flag ab oder setzt es das angibt ob WrapMode TileFlipXY ist.
type: docs
weight: 80
url: /de/net/aspose.words.saving/graphicsqualityoptions/usetileflipmode/
---
## GraphicsQualityOptions.UseTileFlipMode property

Ruft ein Flag ab oder setzt es, das angibt, ob WrapMode TileFlipXY ist.

```csharp
public bool UseTileFlipMode { get; set; }
```

### Bemerkungen

DasWrapMode gibt an, wie eine Textur oder ein Farbverlauf gekachelt wird, wenn er/sie kleiner ist als der zu füllende Bereich.

Standardmäßig verwendetTile (Gibt Kacheln ohne Spiegeln an). Dies führt zu einer ungenauen Wiedergabe des skalierten Bildes (mit hoher Auflösung).

Mit dieser Eigenschaft kann WrapMode auf umgeschaltet werdenTileFlipXY (gibt an, dass Kacheln horizontal gedreht werden, wenn Sie sich entlang einer Reihe bewegen, und vertikal gedreht werden, wenn Sie sich entlang einer Spalte bewegen).

### Beispiele

Zeigt, wie verhindert wird, dass die weiße Linie beim Rendern mit hoher Auflösung erscheint.

```csharp
Document doc = new Document(MyDir + "Shape high dpi.docx");

Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);
ShapeRenderer renderer = shape.GetShapeRenderer();

ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    Resolution = 500, GraphicsQualityOptions = new GraphicsQualityOptions { UseTileFlipMode = true }
};
renderer.Save(ArtifactsDir + "ImageSaveOptions.UseTileFlipMode.png", saveOptions);
```

### Siehe auch

* class [GraphicsQualityOptions](../)
* namensraum [Aspose.Words.Saving](../../graphicsqualityoptions/)
* Montage [Aspose.Words](../../../)


