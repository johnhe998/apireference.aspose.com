---
title: Paragraph.IsEndOfCell
second_title: Référence de l'API Aspose.Words pour .NET
description: Paragraph propriété. Vrai si ce paragraphe est le dernier paragraphe dunCell  faux sinon.
type: docs
weight: 50
url: /fr/net/aspose.words/paragraph/isendofcell/
---
## Paragraph.IsEndOfCell property

Vrai si ce paragraphe est le dernier paragraphe d'un[`Cell`](../../../aspose.words.tables/cell/) ; faux sinon.

```csharp
public bool IsEndOfCell { get; }
```

### Exemples

Montre comment définir une table pour rester ensemble sur la même page.

```csharp
Document doc = new Document(MyDir + "Table spanning two pages.docx");
Table table = doc.FirstSection.Body.Tables[0];

// Activer KeepWithNext pour chaque paragraphe du tableau sauf pour le
// les derniers de la dernière ligne empêcheront le tableau de se diviser sur plusieurs pages.
foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true).OfType<Cell>())
    foreach (Paragraph para in cell.Paragraphs.OfType<Paragraph>())
    {
        Assert.True(para.IsInCell);

        if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
            para.ParagraphFormat.KeepWithNext = true;
    }

doc.Save(ArtifactsDir + "Table.KeepTableTogether.docx");
```

### Voir également

* class [Paragraph](../)
* espace de noms [Aspose.Words](../../paragraph/)
* Assemblée [Aspose.Words](../../../)


