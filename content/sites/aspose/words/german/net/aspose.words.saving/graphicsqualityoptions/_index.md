---
title: Class GraphicsQualityOptions
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Saving.GraphicsQualityOptions klas. Ermöglicht die Angabe zusätzlicherGraphics Qualitätsoptionen.
type: docs
weight: 4780
url: /de/net/aspose.words.saving/graphicsqualityoptions/
---
## GraphicsQualityOptions class

Ermöglicht die Angabe zusätzlicherGraphics Qualitätsoptionen.

```csharp
public class GraphicsQualityOptions
```

## Konstrukteure

| Name | Beschreibung |
| --- | --- |
| [GraphicsQualityOptions](graphicsqualityoptions/)() | Default_Constructor |

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [CompositingMode](../../aspose.words.saving/graphicsqualityoptions/compositingmode/) { get; set; } | Ruft einen Wert ab oder legt einen Wert fest, der angibt, wie zusammengesetzte Bilder zu dieser Grafik gezeichnet werden. |
| [CompositingQuality](../../aspose.words.saving/graphicsqualityoptions/compositingquality/) { get; set; } | Ruft die Renderqualität von zusammengesetzten Bildern ab, die auf diese Grafik gezeichnet wurden, oder legt sie fest. |
| [InterpolationMode](../../aspose.words.saving/graphicsqualityoptions/interpolationmode/) { get; set; } | Ruft den mit dieser Grafik verknüpften Interpolationsmodus ab oder legt ihn fest. |
| [SmoothingMode](../../aspose.words.saving/graphicsqualityoptions/smoothingmode/) { get; set; } | Ruft die Wiedergabequalität für diese Grafik ab oder legt sie fest. |
| [StringFormat](../../aspose.words.saving/graphicsqualityoptions/stringformat/) { get; set; } | Ruft Textlayoutinformationen (wie Ausrichtung, Orientierung und Tabulatoren) ab oder legt sie fest |
| [TextRenderingHint](../../aspose.words.saving/graphicsqualityoptions/textrenderinghint/) { get; set; } | Ruft den Wiedergabemodus für Text ab, der dieser Grafik zugeordnet ist, oder legt ihn fest. |
| [UseTileFlipMode](../../aspose.words.saving/graphicsqualityoptions/usetileflipmode/) { get; set; } | Ruft ein Flag ab oder setzt es, das angibt, ob WrapMode TileFlipXY ist. |

### Beispiele

Zeigt, wie Optionen für die Renderqualität beim Konvertieren von Dokumenten in Bildformate festgelegt werden.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

GraphicsQualityOptions qualityOptions = new GraphicsQualityOptions
{
    SmoothingMode = SmoothingMode.AntiAlias,
    TextRenderingHint = TextRenderingHint.ClearTypeGridFit,
    CompositingMode = CompositingMode.SourceOver,
    CompositingQuality = CompositingQuality.HighQuality,
    InterpolationMode = InterpolationMode.High,
    StringFormat = StringFormat.GenericTypographic
};

ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Jpeg);
saveOptions.GraphicsQualityOptions = qualityOptions;

doc.Save(ArtifactsDir + "ImageSaveOptions.GraphicsQuality.jpg", saveOptions);
```

### Siehe auch

* namensraum [Aspose.Words.Saving](../../aspose.words.saving/)
* Montage [Aspose.Words](../../)


