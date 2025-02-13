---
title: HyphenationOptions.ConsecutiveHyphenLimit
second_title: Aspose.Words för .NET API Referens
description: HyphenationOptions fast egendom. Hämtar eller ställer in det maximala antalet rader i följd som kan sluta med bindestreck. Standardvärdet för den här egenskapen är 0.
type: docs
weight: 30
url: /sv/net/aspose.words.settings/hyphenationoptions/consecutivehyphenlimit/
---
## HyphenationOptions.ConsecutiveHyphenLimit property

Hämtar eller ställer in det maximala antalet rader i följd som kan sluta med bindestreck. Standardvärdet för den här egenskapen är 0.

```csharp
public int ConsecutiveHyphenLimit { get; set; }
```

### Anmärkningar

Om värdet för den här egenskapen är inställt på 0, kan valfritt antal rader i följd sluta med bindestreck.

Egenskapen har ingen effekt när du sparar till fasta sidformat t.ex. PDF.

### Exempel

Visar hur du konfigurerar automatisk avstavning.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Size = 24;
builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

doc.HyphenationOptions.AutoHyphenation = true;
doc.HyphenationOptions.ConsecutiveHyphenLimit = 2;
doc.HyphenationOptions.HyphenationZone = 720;
doc.HyphenationOptions.HyphenateCaps = true;

doc.Save(ArtifactsDir + "Document.HyphenationOptions.docx");
```

### Se även

* class [HyphenationOptions](../)
* namnutrymme [Aspose.Words.Settings](../../hyphenationoptions/)
* hopsättning [Aspose.Words](../../../)


