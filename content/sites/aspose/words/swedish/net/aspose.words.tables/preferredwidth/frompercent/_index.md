---
title: PreferredWidth.FromPercent
second_title: Aspose.Words för .NET API Referens
description: PreferredWidth metod. En skapandemetod som returnerar en ny instans som representerar en föredragen bredd som anges i procent.
type: docs
weight: 20
url: /sv/net/aspose.words.tables/preferredwidth/frompercent/
---
## PreferredWidth.FromPercent method

En skapandemetod som returnerar en ny instans som representerar en föredragen bredd som anges i procent.

```csharp
public static PreferredWidth FromPercent(double percent)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| percent | Double | Värdet måste vara från 0 till 100. |

### Exempel

Visar hur du ställer in en tabell för att automatiskt anpassa till 50 % av sidans bredd.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Cell #1");
builder.InsertCell();
builder.Write("Cell #2");
builder.InsertCell();
builder.Write("Cell #3");

table.PreferredWidth = PreferredWidth.FromPercent(50);

doc.Save(ArtifactsDir + "DocumentBuilder.InsertTableWithPreferredWidth.docx");
```

Visar hur man ställer in en föredragen bredd för tabellceller.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();

// Det finns två sätt att tillämpa klassen "PreferredWidth" på tabellceller.
// 1 - Ställ in en absolut föredragen bredd baserat på punkter:
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln($"Cell with a width of {builder.CellFormat.PreferredWidth}.");

// 2 - Ställ in en relativ föredragen bredd baserat på procent av tabellens bredd:
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln($"Cell with a width of {builder.CellFormat.PreferredWidth}.");

builder.InsertCell();

// En cell utan angiven önskad bredd kommer att ta upp resten av det tillgängliga utrymmet.
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;

// Varje konfiguration av egenskapen "PreferredWidth" skapar ett nytt objekt.
Assert.AreNotEqual(table.FirstRow.Cells[1].CellFormat.PreferredWidth.GetHashCode(),
    builder.CellFormat.PreferredWidth.GetHashCode());

builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Automatically sized cell.");

doc.Save(ArtifactsDir + "DocumentBuilder.InsertCellsWithPreferredWidths.docx");
```

### Se även

* class [PreferredWidth](../)
* namnutrymme [Aspose.Words.Tables](../../preferredwidth/)
* hopsättning [Aspose.Words](../../../)


