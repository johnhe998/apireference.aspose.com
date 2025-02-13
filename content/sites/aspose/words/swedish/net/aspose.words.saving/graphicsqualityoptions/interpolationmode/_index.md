---
title: GraphicsQualityOptions.InterpolationMode
second_title: Aspose.Words för .NET API Referens
description: GraphicsQualityOptions fast egendom. Hämtar eller ställer in interpolationsläget som är associerat med denna grafik.
type: docs
weight: 40
url: /sv/net/aspose.words.saving/graphicsqualityoptions/interpolationmode/
---
## GraphicsQualityOptions.InterpolationMode property

Hämtar eller ställer in interpolationsläget som är associerat med denna grafik.

```csharp
public InterpolationMode? InterpolationMode { get; set; }
```

### Exempel

Visar hur du ställer in alternativ för återgivningskvalitet när du konverterar dokument till bildformat.

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

### Se även

* class [GraphicsQualityOptions](../)
* namnutrymme [Aspose.Words.Saving](../../graphicsqualityoptions/)
* hopsättning [Aspose.Words](../../../)


