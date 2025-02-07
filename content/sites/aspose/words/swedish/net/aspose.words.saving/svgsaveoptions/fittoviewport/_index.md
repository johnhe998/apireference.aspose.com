---
title: SvgSaveOptions.FitToViewPort
second_title: Aspose.Words för .NET API Referens
description: SvgSaveOptions fast egendom. Anger om utdataSVG ska fylla det tillgängliga viewportområdet webbläsarfönster eller behållare. När den är inställd på sann bredd och höjd på utdata är SVG inställda på 100.
type: docs
weight: 30
url: /sv/net/aspose.words.saving/svgsaveoptions/fittoviewport/
---
## SvgSaveOptions.FitToViewPort property

Anger om utdata-SVG ska fylla det tillgängliga viewportområdet (webbläsarfönster eller behållare). När den är inställd på sann bredd och höjd på utdata är SVG inställda på 100%.

Standardvärdet är falskt.

```csharp
public bool FitToViewPort { get; set; }
```

### Exempel

Visar hur man efterliknar egenskaperna hos bilder när man konverterar ett .docx-dokument till .svg.

```csharp
Document doc = new Document(MyDir + "Document.docx");

// Konfigurera SvgSaveOptions-objektet för att spara utan sidkanter eller valbar text.
SvgSaveOptions options = new SvgSaveOptions
{
    FitToViewPort = true,
    ShowPageBorder = false,
    TextOutputMode = SvgTextOutputMode.UsePlacedGlyphs
};

doc.Save(ArtifactsDir + "SvgSaveOptions.SaveLikeImage.svg", options);
```

### Se även

* class [SvgSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../svgsaveoptions/)
* hopsättning [Aspose.Words](../../../)


