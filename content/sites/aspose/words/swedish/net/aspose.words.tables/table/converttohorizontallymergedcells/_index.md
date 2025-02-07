---
title: Table.ConvertToHorizontallyMergedCells
second_title: Aspose.Words för .NET API Referens
description: Table metod. Konverterar celler horisontellt sammanfogade efter bredd till celler sammanslagna avHorizontalMerge .
type: docs
weight: 390
url: /sv/net/aspose.words.tables/table/converttohorizontallymergedcells/
---
## Table.ConvertToHorizontallyMergedCells method

Konverterar celler horisontellt sammanfogade efter bredd till celler sammanslagna av[`HorizontalMerge`](../../cellformat/horizontalmerge/) .

```csharp
public void ConvertToHorizontallyMergedCells()
```

### Anmärkningar

Tabellceller kan slås samman horisontellt antingen genom att använda sammanslagningsflaggor[`HorizontalMerge`](../../cellformat/horizontalmerge/) eller med cellbredd[`Width`](../../cellformat/width/).

När tabellcell slås samman med egenskapen width[`HorizontalMerge`](../../cellformat/horizontalmerge/) är meningslöst men ibland är det ett bekvämare sätt att ha sammanslagningsflaggor.

Använd den här metoden för att omvandla tabellceller horisontellt sammanslagna efter bredd till celler sammanslagna med sammanslagningsflaggor.

### Exempel

Visar hur man konverterar celler horisontellt sammanfogade efter bredd till celler sammanslagna av CellFormat.HorizontalMerge.

```csharp
Document doc = new Document(MyDir + "Table with merged cells.docx");

// Microsoft Word skriver inte merge-flaggor längre, utan definierar sammanslagna celler efter bredd istället.
// Aspose.Words definierar som standard endast 5 celler i rad, och ingen av dem har den horisontella sammanslagningsflaggan,
// även om det fanns 7 celler i raden innan den horisontella sammanslagningen ägde rum.
Table table = doc.FirstSection.Body.Tables[0];
Row row = table.Rows[0];

Assert.AreEqual(5, row.Cells.Count);
Assert.True(row.Cells.All(c => ((Cell)c).CellFormat.HorizontalMerge == CellMerge.None));

// Använd metoden "ConvertToHorizontallyMergedCells" för att konvertera celler horisontellt sammanslagna
// av dess bredd till cellen horisontellt sammanfogad av flaggor.
// Nu har vi 7 celler, och några av dem har horisontella sammanslagningsvärden.
table.ConvertToHorizontallyMergedCells();
row = table.Rows[0];

Assert.AreEqual(7, row.Cells.Count);

Assert.AreEqual(CellMerge.None, row.Cells[0].CellFormat.HorizontalMerge);
Assert.AreEqual(CellMerge.First, row.Cells[1].CellFormat.HorizontalMerge);
Assert.AreEqual(CellMerge.Previous, row.Cells[2].CellFormat.HorizontalMerge);
Assert.AreEqual(CellMerge.None, row.Cells[3].CellFormat.HorizontalMerge);
Assert.AreEqual(CellMerge.First, row.Cells[4].CellFormat.HorizontalMerge);
Assert.AreEqual(CellMerge.Previous, row.Cells[5].CellFormat.HorizontalMerge);
Assert.AreEqual(CellMerge.None, row.Cells[6].CellFormat.HorizontalMerge);
```

### Se även

* class [Table](../)
* namnutrymme [Aspose.Words.Tables](../../table/)
* hopsättning [Aspose.Words](../../../)


