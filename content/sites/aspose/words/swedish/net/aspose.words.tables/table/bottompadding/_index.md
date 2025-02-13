---
title: Table.BottomPadding
second_title: Aspose.Words för .NET API Referens
description: Table fast egendom. Hämtar eller ställer in mängden utrymme i poäng som ska läggas till under innehållet i celler.
type: docs
weight: 90
url: /sv/net/aspose.words.tables/table/bottompadding/
---
## Table.BottomPadding property

Hämtar eller ställer in mängden utrymme (i poäng) som ska läggas till under innehållet i celler.

```csharp
public double BottomPadding { get; set; }
```

### Exempel

Visar hur man konfigurerar innehållsutfyllnad i en tabell.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Row 1, cell 1.");
builder.InsertCell();
builder.Write("Row 1, cell 2.");
builder.EndTable();

// För varje cell i tabellen, ställ in avståndet mellan dess innehåll och var och en av dess kanter. 
// Den här tabellen kommer att bibehålla det minsta utfyllnadsavståndet genom att slå in text.
table.LeftPadding = 30;
table.RightPadding = 60;
table.TopPadding = 10;
table.BottomPadding = 90;
table.PreferredWidth = PreferredWidth.FromPoints(250);

doc.Save(ArtifactsDir + "DocumentBuilder.SetRowFormatting.docx");
```

### Se även

* class [Table](../)
* namnutrymme [Aspose.Words.Tables](../../table/)
* hopsättning [Aspose.Words](../../../)


