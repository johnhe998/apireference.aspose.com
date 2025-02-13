---
title: ConditionalStyle.ClearFormatting
second_title: Aspose.Words för .NET API Referens
description: ConditionalStyle metod. Rensar formateringen av denna villkorliga stil.
type: docs
weight: 100
url: /sv/net/aspose.words/conditionalstyle/clearformatting/
---
## ConditionalStyle.ClearFormatting method

Rensar formateringen av denna villkorliga stil.

```csharp
public void ClearFormatting()
```

### Exempel

Visar hur man återställer villkorliga tabellstilar.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("First row");
builder.EndRow();
builder.InsertCell();
builder.Write("Last row");
builder.EndTable();

TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
table.Style = tableStyle;

// Ställ in tabellstilen för att färga kanterna på den första raden i tabellen i rött.
tableStyle.ConditionalStyles.FirstRow.Borders.Color = Color.Red;

// Ställ in tabellstilen för att färga kanterna på den sista raden i tabellen i blått.
tableStyle.ConditionalStyles.LastRow.Borders.Color = Color.Blue;

// Nedan finns två sätt att använda "ClearFormatting"-metoden för att rensa de villkorliga stilarna.
// 1 - Rensa de villkorliga stilarna för en specifik del av en tabell:
tableStyle.ConditionalStyles[0].ClearFormatting();

Assert.AreEqual(Color.Empty, tableStyle.ConditionalStyles.FirstRow.Borders.Color);

// 2 - Rensa de villkorliga stilarna för hela tabellen:
tableStyle.ConditionalStyles.ClearFormatting();

Assert.True(tableStyle.ConditionalStyles.All(s => s.Borders.Color == Color.Empty));
```

### Se även

* class [ConditionalStyle](../)
* namnutrymme [Aspose.Words](../../conditionalstyle/)
* hopsättning [Aspose.Words](../../../)


