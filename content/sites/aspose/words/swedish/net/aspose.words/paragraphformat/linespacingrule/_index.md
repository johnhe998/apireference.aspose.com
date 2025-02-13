---
title: ParagraphFormat.LineSpacingRule
second_title: Aspose.Words för .NET API Referens
description: ParagraphFormat fast egendom. Hämtar eller ställer in radavståndet för stycket.
type: docs
weight: 190
url: /sv/net/aspose.words/paragraphformat/linespacingrule/
---
## ParagraphFormat.LineSpacingRule property

Hämtar eller ställer in radavståndet för stycket.

```csharp
public LineSpacingRule LineSpacingRule { get; set; }
```

### Exempel

Visar hur man arbetar med radavstånd.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Nedan finns tre radavståndsregler som vi kan definiera med hjälp av
// styckets "LineSpacingRule"-egenskap för att konfigurera avståndet mellan stycken.
// 1 - Ställ in ett minsta avstånd.
// Detta kommer att ge vertikal utfyllnad till textrader av valfri storlek
// som är för liten för att bibehålla den lägsta linjehöjden.
builder.ParagraphFormat.LineSpacingRule = LineSpacingRule.AtLeast;
builder.ParagraphFormat.LineSpacing = 20;

builder.Writeln("Minimum line spacing of 20.");
builder.Writeln("Minimum line spacing of 20.");

// 2 - Ställ in exakt avstånd.
// Om du använder teckenstorlekar som är för stora för avståndet kommer texten att trunkeras.
builder.ParagraphFormat.LineSpacingRule = LineSpacingRule.Exactly;
builder.ParagraphFormat.LineSpacing = 5;

builder.Writeln("Line spacing of exactly 5.");
builder.Writeln("Line spacing of exactly 5.");

// 3 - Ange avstånd som en multipel av standard radavstånd, vilket är 12 punkter som standard.
// Den här typen av mellanrum kommer att skalas till olika teckenstorlekar.
builder.ParagraphFormat.LineSpacingRule = LineSpacingRule.Multiple;
builder.ParagraphFormat.LineSpacing = 18;

builder.Writeln("Line spacing of 1.5 default lines.");
builder.Writeln("Line spacing of 1.5 default lines.");

doc.Save(ArtifactsDir + "ParagraphFormat.LineSpacing.docx");
```

### Se även

* enum [LineSpacingRule](../../linespacingrule/)
* class [ParagraphFormat](../)
* namnutrymme [Aspose.Words](../../paragraphformat/)
* hopsättning [Aspose.Words](../../../)


