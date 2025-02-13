---
title: Enum PreferredWidthType
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Tables.PreferredWidthType uppräkning. Anger måttenheten för den föredragna bredden på en tabell eller cell.
type: docs
weight: 6000
url: /sv/net/aspose.words.tables/preferredwidthtype/
---
## PreferredWidthType enumeration

Anger måttenheten för den föredragna bredden på en tabell eller cell.

```csharp
public enum PreferredWidthType
```

### Värderingar

| namn | Värde | Beskrivning |
| --- | --- | --- |
| Auto | `1` | Den föredragna bredden är inte specificerad. Tabellens eller cellens faktiska bredd anges antingen med den explicita bredden eller så bestäms automatiskt av tabelllayoutalgoritmen när tabellen visas, beroende på inställningen för automatisk anpassning av tabellen. |
| Percent | `2` | Mät den aktuella artikelns bredd med en angiven procentandel. |
| Points | `3` | Mät den aktuella artikelns bredd med ett angivet antal punkter (1/72 tum). |

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

* class [PreferredWidth](../preferredwidth/)
* namnutrymme [Aspose.Words.Tables](../../aspose.words.tables/)
* hopsättning [Aspose.Words](../../)


