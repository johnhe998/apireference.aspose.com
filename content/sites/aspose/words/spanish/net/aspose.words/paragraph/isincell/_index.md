---
title: Paragraph.IsInCell
second_title: Referencia de API de Aspose.Words para .NET
description: Paragraph propiedad. Verdadero si este párrafo es un hijo inmediato deCell  falso en caso contrario.
type: docs
weight: 100
url: /es/net/aspose.words/paragraph/isincell/
---
## Paragraph.IsInCell property

Verdadero si este párrafo es un hijo inmediato de[`Cell`](../../../aspose.words.tables/cell/) ; falso en caso contrario.

```csharp
public bool IsInCell { get; }
```

### Ejemplos

Muestra cómo configurar una mesa para permanecer juntos en la misma página.

```csharp
Document doc = new Document(MyDir + "Table spanning two pages.docx");
Table table = doc.FirstSection.Body.Tables[0];

// Habilitar KeepWithNext para cada párrafo de la tabla excepto para el
// los últimos en la última fila evitarán que la tabla se divida en varias páginas.
foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true).OfType<Cell>())
    foreach (Paragraph para in cell.Paragraphs.OfType<Paragraph>())
    {
        Assert.True(para.IsInCell);

        if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
            para.ParagraphFormat.KeepWithNext = true;
    }

doc.Save(ArtifactsDir + "Table.KeepTableTogether.docx");
```

### Ver también

* class [Paragraph](../)
* espacio de nombres [Aspose.Words](../../paragraph/)
* asamblea [Aspose.Words](../../../)


