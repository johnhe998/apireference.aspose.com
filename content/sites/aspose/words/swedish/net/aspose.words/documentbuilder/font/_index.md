---
title: DocumentBuilder.Font
second_title: Aspose.Words för .NET API Referens
description: DocumentBuilder fast egendom. Returnerar ett objekt som representerar aktuella teckensnittsformateringsegenskaper.
type: docs
weight: 90
url: /sv/net/aspose.words/documentbuilder/font/
---
## DocumentBuilder.Font property

Returnerar ett objekt som representerar aktuella teckensnittsformateringsegenskaper.

```csharp
public Font Font { get; }
```

### Anmärkningar

Använda sig av **Font** för att komma åt och ändra teckensnittsformateringsegenskaper.

Ange teckensnittsformatering innan du infogar text.

### Exempel

Visar hur man infogar en sträng omgiven av en kant i ett dokument.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Border.Color = Color.Green;
builder.Font.Border.LineWidth = 2.5d;
builder.Font.Border.LineStyle = LineStyle.DashDotStroker;

builder.Write("Text surrounded by green border.");

doc.Save(ArtifactsDir + "Border.FontBorder.docx");
```

Visar hur man skapar en formaterad tabell med DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.LeftIndent = 20;

// Ställ in några formateringsalternativ för text och tabellutseende.
builder.RowFormat.Height = 40;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;

// Konfigurering av formateringsalternativen i en dokumentbyggare kommer att tillämpa dem
// till den aktuella cellen/raden dess markör är i,
// samt eventuella nya celler och rader skapade med hjälp av den byggaren.
builder.Write("Header Row,\n Cell 1");
builder.InsertCell();
builder.Write("Header Row,\n Cell 2");
builder.InsertCell();
builder.Write("Header Row,\n Cell 3");
builder.EndRow();

// Konfigurera om byggarens formateringsobjekt för nya rader och celler som vi håller på att göra.
// Byggaren kommer inte att tillämpa dessa på den första raden som redan skapats så att den kommer att sticka ut som en rubrikrad.
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30;
builder.RowFormat.HeightRule = HeightRule.Auto;
builder.InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;

builder.Write("Row 1, Cell 1.");
builder.InsertCell();
builder.Write("Row 1, Cell 2.");
builder.InsertCell();
builder.Write("Row 1, Cell 3.");
builder.EndRow();
builder.InsertCell();
builder.Write("Row 2, Cell 1.");
builder.InsertCell();
builder.Write("Row 2, Cell 2.");
builder.InsertCell();
builder.Write("Row 2, Cell 3.");
builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "DocumentBuilder.CreateFormattedTable.docx");
```

### Se även

* class [Font](../../font/)
* class [DocumentBuilder](../)
* namnutrymme [Aspose.Words](../../documentbuilder/)
* hopsättning [Aspose.Words](../../../)


