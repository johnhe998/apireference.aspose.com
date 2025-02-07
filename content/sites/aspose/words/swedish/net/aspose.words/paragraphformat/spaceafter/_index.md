---
title: ParagraphFormat.SpaceAfter
second_title: Aspose.Words för .NET API Referens
description: ParagraphFormat fast egendom. Hämtar eller ställer in mängden mellanrum i poäng efter stycket.
type: docs
weight: 290
url: /sv/net/aspose.words/paragraphformat/spaceafter/
---
## ParagraphFormat.SpaceAfter property

Hämtar eller ställer in mängden mellanrum (i poäng) efter stycket.

```csharp
public double SpaceAfter { get; set; }
```

### Undantag

| undantag | skick |
| --- | --- |
| ArgumentOutOfRangeException | Kastar när argumentet var utanför intervallet för giltiga värden. |

### Anmärkningar

Har ingen effekt när[`SpaceAfterAuto`](../spaceafterauto/) är sant.

Giltiga värden sträcker sig från 0 till 1584 inklusive.

### Exempel

Visar hur man ställer in automatiskt styckeavstånd.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Använd en stor mängd mellanrum före och efter stycken som den här byggaren kommer att skapa.
builder.ParagraphFormat.SpaceBefore = 24;
builder.ParagraphFormat.SpaceAfter = 24;

// Ställ in dessa flaggor på "true" för att tillämpa automatiskt mellanrum,
// ignorerar effektivt avståndet i egenskaperna vi ställt in ovan.
// Lämna dem som "false" kommer att tillämpa vårt anpassade styckeavstånd.
builder.ParagraphFormat.SpaceAfterAuto = autoSpacing;
builder.ParagraphFormat.SpaceBeforeAuto = autoSpacing;

// Infoga två stycken som kommer att ha mellanrum ovanför och under dem och spara dokumentet.
builder.Writeln("Paragraph 1.");
builder.Writeln("Paragraph 2.");

doc.Save(ArtifactsDir + "ParagraphFormat.ParagraphSpacingAuto.docx");
```

Visar hur man inte använder mellanrum mellan stycken med samma stil.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Använd en stor mängd mellanrum före och efter stycken som den här byggaren kommer att skapa.
builder.ParagraphFormat.SpaceBefore = 24;
builder.ParagraphFormat.SpaceAfter = 24;

// Ställ in "NoSpaceBetweenParagraphsOfSameStyle"-flaggan till "true" för att tillämpa
// inget mellanrum mellan stycken med samma stil, vilket kommer att gruppera liknande stycken.
// Lämna flaggan "NoSpaceBetweenParagraphsOfSameStyle" som "false"
// för att jämnt tillämpa mellanrum på varje stycke.
builder.ParagraphFormat.NoSpaceBetweenParagraphsOfSameStyle = noSpaceBetweenParagraphsOfSameStyle;

builder.ParagraphFormat.Style = doc.Styles["Normal"];
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.ParagraphFormat.Style = doc.Styles["Quote"];
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.ParagraphFormat.Style = doc.Styles["Normal"];
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");

doc.Save(ArtifactsDir + "ParagraphFormat.ParagraphSpacingSameStyle.docx");
```

### Se även

* class [ParagraphFormat](../)
* namnutrymme [Aspose.Words](../../paragraphformat/)
* hopsättning [Aspose.Words](../../../)


