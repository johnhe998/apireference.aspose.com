---
title: Font.Name
second_title: Aspose.Words för .NET API Referens
description: Font fast egendom. Hämtar eller ställer in namnet på teckensnittet.
type: docs
weight: 230
url: /sv/net/aspose.words/font/name/
---
## Font.Name property

Hämtar eller ställer in namnet på teckensnittet.

```csharp
public string Name { get; set; }
```

### Anmärkningar

När man får, återkommer[`NameAscii`](../nameascii/).

Vid inställning, ställer in[`NameAscii`](../nameascii/) ,[`NameBi`](../namebi/) ,[`NameFarEast`](../namefareast/) och[`NameOther`](../nameother/) till det angivna värdet.

### Exempel

Visar hur man formaterar en serie text med dess teckensnittsegenskap.

```csharp
Document doc = new Document();
Run run = new Run(doc, "Hello world!");

Aspose.Words.Font font = run.Font;
font.Name = "Courier New";
font.Size = 36;
font.HighlightColor = Color.Yellow;

doc.FirstSection.Body.FirstParagraph.AppendChild(run);
doc.Save(ArtifactsDir + "Font.CreateFormattedRun.docx");
```

Visar hur man infogar formaterad text med DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ange teckensnittsformatering och lägg sedan till text.
Aspose.Words.Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Courier New";
font.Underline = Underline.Dash;

builder.Write("Hello world!");
```

### Se även

* class [Font](../)
* namnutrymme [Aspose.Words](../../font/)
* hopsättning [Aspose.Words](../../../)


