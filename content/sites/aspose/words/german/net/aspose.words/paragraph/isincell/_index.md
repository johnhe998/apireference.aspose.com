---
title: Paragraph.IsInCell
second_title: Aspose.Words für .NET-API-Referenz
description: Paragraph eigendom. Wahr wenn dieser Absatz ein direktes Kind von istCell  andernfalls falsch.
type: docs
weight: 100
url: /de/net/aspose.words/paragraph/isincell/
---
## Paragraph.IsInCell property

Wahr, wenn dieser Absatz ein direktes Kind von ist[`Cell`](../../../aspose.words.tables/cell/) ; andernfalls falsch.

```csharp
public bool IsInCell { get; }
```

### Beispiele

Zeigt, wie man einen Tisch so einrichtet, dass er zusammen auf der gleichen Seite bleibt.

```csharp
Document doc = new Document(MyDir + "Table spanning two pages.docx");
Table table = doc.FirstSection.Body.Tables[0];

// Aktiviere KeepWithNext für jeden Absatz in der Tabelle außer dem
// Die letzten in der letzten Zeile verhindern, dass die Tabelle auf mehrere Seiten aufgeteilt wird.
foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true).OfType<Cell>())
    foreach (Paragraph para in cell.Paragraphs.OfType<Paragraph>())
    {
        Assert.True(para.IsInCell);

        if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
            para.ParagraphFormat.KeepWithNext = true;
    }

doc.Save(ArtifactsDir + "Table.KeepTableTogether.docx");
```

### Siehe auch

* class [Paragraph](../)
* namensraum [Aspose.Words](../../paragraph/)
* Montage [Aspose.Words](../../../)


