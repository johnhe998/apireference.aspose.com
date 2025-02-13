---
title: Cell.Paragraphs
second_title: Aspose.Words för .NET API Referens
description: Cell fast egendom. Får en samling stycken som är omedelbara barn till cellen.
type: docs
weight: 80
url: /sv/net/aspose.words.tables/cell/paragraphs/
---
## Cell.Paragraphs property

Får en samling stycken som är omedelbara barn till cellen.

```csharp
public ParagraphCollection Paragraphs { get; }
```

### Exempel

Visar hur man ställer in ett bord för att hålla ihop på samma sida.

```csharp
Document doc = new Document(MyDir + "Table spanning two pages.docx");
Table table = doc.FirstSection.Body.Tables[0];

// Aktivera KeepWithNext för varje stycke i tabellen utom för
// de sista i den sista raden kommer att förhindra att tabellen delas upp på flera sidor.
foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true).OfType<Cell>())
    foreach (Paragraph para in cell.Paragraphs.OfType<Paragraph>())
    {
        Assert.True(para.IsInCell);

        if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
            para.ParagraphFormat.KeepWithNext = true;
    }

doc.Save(ArtifactsDir + "Table.KeepTableTogether.docx");
```

### Se även

* class [ParagraphCollection](../../../aspose.words/paragraphcollection/)
* class [Cell](../)
* namnutrymme [Aspose.Words.Tables](../../cell/)
* hopsättning [Aspose.Words](../../../)


