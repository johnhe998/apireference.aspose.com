---
title: SvgSaveOptions.TextOutputMode
second_title: Aspose.Words för .NET API Referens
description: SvgSaveOptions fast egendom. Hämtar eller ställer in ett värde som bestämmer hur text ska renderas i SVG.
type: docs
weight: 90
url: /sv/net/aspose.words.saving/svgsaveoptions/textoutputmode/
---
## SvgSaveOptions.TextOutputMode property

Hämtar eller ställer in ett värde som bestämmer hur text ska renderas i SVG.

```csharp
public SvgTextOutputMode TextOutputMode { get; set; }
```

### Anmärkningar

Använd den här egenskapen för att hämta eller ställa in läget för hur text i ett dokument ska renderas när du sparar i SVG-format.

Standardvärdet ärUseTargetMachineFonts.

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

* enum [SvgTextOutputMode](../../svgtextoutputmode/)
* class [SvgSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../svgsaveoptions/)
* hopsättning [Aspose.Words](../../../)


