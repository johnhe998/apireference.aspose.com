---
title: Table.SetBorders
second_title: Aspose.Words för .NET API Referens
description: Table metod. Ställer in alla tabellkanter till angiven linjestil bredd och färg.
type: docs
weight: 420
url: /sv/net/aspose.words.tables/table/setborders/
---
## Table.SetBorders method

Ställer in alla tabellkanter till angiven linjestil, bredd och färg.

```csharp
public void SetBorders(LineStyle lineStyle, double lineWidth, Color color)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| lineStyle | LineStyle | Linjestilen som ska tillämpas. |
| lineWidth | Double | Linjebredden som ska ställas in (i punkter). |
| color | Color | Färgen som ska användas för bården. |

### Exempel

Visar hur man formaterar alla en tabells ramar samtidigt.

```csharp
Document doc = new Document(MyDir + "Tables.docx");
Table table = doc.FirstSection.Body.Tables[0];

// Rensa alla befintliga gränser från tabellen.
table.ClearBorders();

// Sätt en enda grön linje för att fungera som varje yttre och inre kant av detta bord.
table.SetBorders(LineStyle.Single, 1.5, Color.Green);

doc.Save(ArtifactsDir + "Table.SetBorders.docx");
```

Visar hur man applicerar kant- och skuggfärg när man bygger ett bord.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Starta en tabell och ställ in en standardfärg/tjocklek för dess kanter.
Table table = builder.StartTable();
table.SetBorders(LineStyle.Single, 2.0, Color.Black);

// Skapa en rad med två celler med olika bakgrundsfärger.
builder.InsertCell();
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightSkyBlue;
builder.Writeln("Row 1, Cell 1.");
builder.InsertCell();
builder.CellFormat.Shading.BackgroundPatternColor = Color.Orange;
builder.Writeln("Row 1, Cell 2.");
builder.EndRow();

// Återställ cellformateringen för att inaktivera bakgrundsfärgerna
// ställ in en anpassad kanttjocklek för alla nya celler skapade av byggaren,
// bygg sedan en andra rad.
builder.CellFormat.ClearFormatting();
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;

builder.InsertCell();
builder.Writeln("Row 2, Cell 1.");
builder.InsertCell();
builder.Writeln("Row 2, Cell 2.");

doc.Save(ArtifactsDir + "DocumentBuilder.TableBordersAndShading.docx");
```

### Se även

* enum [LineStyle](../../../aspose.words/linestyle/)
* class [Table](../)
* namnutrymme [Aspose.Words.Tables](../../table/)
* hopsättning [Aspose.Words](../../../)


