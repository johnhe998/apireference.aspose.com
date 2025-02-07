---
title: HyphenationOptions.HyphenationZone
second_title: Aspose.Words för .NET API Referens
description: HyphenationOptions fast egendom. Hämtar eller ställer in avståndet i 1/20 av en punkt från högermarginalen inom vilken du inte vill att ska avstava ord. Standardvärdet för den här egenskapen är 360 025 tum.
type: docs
weight: 50
url: /sv/net/aspose.words.settings/hyphenationoptions/hyphenationzone/
---
## HyphenationOptions.HyphenationZone property

Hämtar eller ställer in avståndet i 1/20 av en punkt från högermarginalen inom vilken du inte vill att ska avstava ord. Standardvärdet för den här egenskapen är 360 (0,25 tum).

```csharp
public int HyphenationZone { get; set; }
```

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


