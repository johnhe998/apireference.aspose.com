---
title: Paragraph.IsEndOfCell
second_title: Aspose.Words per .NET API Reference
description: Paragraph proprietà. Vero se questo paragrafo è lultimo paragrafo in aCell  falso altrimenti.
type: docs
weight: 50
url: /it/net/aspose.words/paragraph/isendofcell/
---
## Paragraph.IsEndOfCell property

Vero se questo paragrafo è l'ultimo paragrafo in a[`Cell`](../../../aspose.words.tables/cell/) ; falso altrimenti.

```csharp
public bool IsEndOfCell { get; }
```

### Esempi

Mostra come impostare un tavolo per stare insieme sulla stessa pagina.

```csharp
Document doc = new Document(MyDir + "Table spanning two pages.docx");
Table table = doc.FirstSection.Body.Tables[0];

// Abilitazione KeepWithNext per ogni paragrafo della tabella ad eccezione di
// gli ultimi nell'ultima riga impediranno alla tabella di dividersi su più pagine.
foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true).OfType<Cell>())
    foreach (Paragraph para in cell.Paragraphs.OfType<Paragraph>())
    {
        Assert.True(para.IsInCell);

        if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
            para.ParagraphFormat.KeepWithNext = true;
    }

doc.Save(ArtifactsDir + "Table.KeepTableTogether.docx");
```

### Guarda anche

* class [Paragraph](../)
* spazio dei nomi [Aspose.Words](../../paragraph/)
* assemblea [Aspose.Words](../../../)


