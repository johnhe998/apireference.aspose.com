---
title: SvgSaveOptions.ShowPageBorder
second_title: Aspose.Words för .NET API Referens
description: SvgSaveOptions fast egendom. Styr om en ram läggs till i konturen av sidan. Standard ärSann .
type: docs
weight: 80
url: /sv/net/aspose.words.saving/svgsaveoptions/showpageborder/
---
## SvgSaveOptions.ShowPageBorder property

Styr om en ram läggs till i konturen av sidan. Standard är`Sann` .

```csharp
public bool ShowPageBorder { get; set; }
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


