---
title: CellFormat.PreferredWidth
second_title: Aspose.Words för .NET API Referens
description: CellFormat fast egendom. Returnerar eller ställer in önskad bredd på cellen.
type: docs
weight: 70
url: /sv/net/aspose.words.tables/cellformat/preferredwidth/
---
## CellFormat.PreferredWidth property

Returnerar eller ställer in önskad bredd på cellen.

```csharp
public PreferredWidth PreferredWidth { get; set; }
```

### Anmärkningar

Den föredragna bredden (tillsammans med tabellens Autopassningsalternativ) bestämmer hur den faktiska bredden på cellen beräknas av tabelllayoutalgoritmen. Tabelllayout kan utföras av Aspose.Words när det sparar dokumentet eller av Microsoft Word när det visar dokumentet.

Den föredragna bredden kan anges i punkter eller i procent. Den föredragna width kan också anges som "auto", vilket betyder att ingen föredragen bredd är angiven.

Standardvärdet är[`Auto`](../../preferredwidth/auto/).

### Exempel

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

* class [PreferredWidth](../../preferredwidth/)
* class [CellFormat](../)
* namnutrymme [Aspose.Words.Tables](../../cellformat/)
* hopsättning [Aspose.Words](../../../)


