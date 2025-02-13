---
title: Cell.EnsureMinimum
second_title: Aspose.Words för .NET API Referens
description: Cell metod. Om det sista underordnade inte är ett stycke skapar och lägger till ett tomt stycke.
type: docs
weight: 120
url: /sv/net/aspose.words.tables/cell/ensureminimum/
---
## Cell.EnsureMinimum method

Om det sista underordnade inte är ett stycke, skapar och lägger till ett tomt stycke.

```csharp
public void EnsureMinimum()
```

### Exempel

Visar hur man säkerställer att en cellnod innehåller de noder vi behöver för att börja lägga till innehåll till den.

```csharp
Document doc = new Document();
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
Row row = new Row(doc);
table.AppendChild(row);
Cell cell = new Cell(doc);
row.AppendChild(cell);

// Celler kan innehålla stycken med typiska element som körningar, former och till och med andra tabeller.
// Vår nya cell har inga stycken, och vi kan inte lägga till innehåll som kör- och formnoder till den förrän den gör det.
Assert.AreEqual(0, cell.GetChildNodes(NodeType.Any, true).Count);

// Att anropa metoden "EnsureMinimum" på en cell säkerställer det
// cellen har minst ett tomt stycke, som vi sedan kan lägga till innehåll till.
cell.EnsureMinimum();
cell.FirstParagraph.AppendChild(new Run(doc, "Hello world!"));
```

### Se även

* class [Cell](../)
* namnutrymme [Aspose.Words.Tables](../../cell/)
* hopsättning [Aspose.Words](../../../)


