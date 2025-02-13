---
title: Font.Kerning
second_title: Aspose.Words för .NET API Referens
description: Font fast egendom. Hämtar eller ställer in teckenstorleken vid vilken kerning startar.
type: docs
weight: 180
url: /sv/net/aspose.words/font/kerning/
---
## Font.Kerning property

Hämtar eller ställer in teckenstorleken vid vilken kerning startar.

```csharp
public double Kerning { get; set; }
```

### Exempel

Visar hur man anger teckenstorleken vid vilken kerning börjar träda i kraft.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial Black";

// Ställ in byggarens teckensnittsstorlek och minimistorlek vid vilken kerning ska träda i kraft.
// Teckenstorleken faller under kerning-tröskeln, så körningen nedan kommer inte att ha kerning.
builder.Font.Size = 18;
builder.Font.Kerning = 24;

builder.Writeln("TALLY. (Kerning not applied)");

// Ställ in kerning-tröskeln så att byggarens nuvarande teckenstorlek är över den.
// All text vi lägger till från denna punkt kommer att ha kerning tillämpad. Mellanrummen mellan tecken
// kommer att justeras, vilket normalt resulterar i en något mer estetiskt tilltalande textkörning.
builder.Font.Kerning = 12;

builder.Writeln("TALLY. (Kerning applied)");

doc.Save(ArtifactsDir + "Font.Kerning.docx");
```

### Se även

* class [Font](../)
* namnutrymme [Aspose.Words](../../font/)
* hopsättning [Aspose.Words](../../../)


