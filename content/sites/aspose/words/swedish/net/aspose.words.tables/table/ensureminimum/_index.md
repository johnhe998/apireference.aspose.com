---
title: Table.EnsureMinimum
second_title: Aspose.Words för .NET API Referens
description: Table metod. Om tabellen inte har några rader skapar och lägger till en Rad .
type: docs
weight: 400
url: /sv/net/aspose.words.tables/table/ensureminimum/
---
## Table.EnsureMinimum method

Om tabellen inte har några rader, skapar och lägger till en **Rad** .

```csharp
public void EnsureMinimum()
```

### Exempel

Visar hur man säkerställer att en tabellnod innehåller de noder vi behöver för att lägga till innehåll.

```csharp
Document doc = new Document();
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);

// Tabeller innehåller rader, som innehåller celler, som kan innehålla stycken
// med typiska element som körningar, former och till och med andra tabeller.
// Vår nya tabell har ingen av dessa noder, och vi kan inte lägga till innehåll till den förrän den gör det.
Assert.AreEqual(0, table.GetChildNodes(NodeType.Any, true).Count);

// Att anropa metoden "EnsureMinimum" på en tabell säkerställer det
// tabellen har minst en rad och en cell med ett tomt stycke.
table.EnsureMinimum();
table.FirstRow.FirstCell.FirstParagraph.AppendChild(new Run(doc, "Hello world!"));
```

### Se även

* class [Table](../)
* namnutrymme [Aspose.Words.Tables](../../table/)
* hopsättning [Aspose.Words](../../../)


