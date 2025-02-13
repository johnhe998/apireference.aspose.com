---
title: PreferredWidth.Value
second_title: Aspose.Words för .NET API Referens
description: PreferredWidth fast egendom. Hämtar önskat breddvärde. Måttenheten anges iType egenskap.
type: docs
weight: 50
url: /sv/net/aspose.words.tables/preferredwidth/value/
---
## PreferredWidth.Value property

Hämtar önskat breddvärde. Måttenheten anges i[`Type`](../type/) egenskap.

```csharp
public double Value { get; }
```

### Exempel

Visar hur man verifierar den föredragna breddtypen och värdet för en tabellcell.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

Table table = doc.FirstSection.Body.Tables[0];
Cell firstCell = table.FirstRow.FirstCell;

Assert.AreEqual(PreferredWidthType.Percent, firstCell.CellFormat.PreferredWidth.Type);
Assert.AreEqual(11.16d, firstCell.CellFormat.PreferredWidth.Value);
```

### Se även

* class [PreferredWidth](../)
* namnutrymme [Aspose.Words.Tables](../../preferredwidth/)
* hopsättning [Aspose.Words](../../../)


