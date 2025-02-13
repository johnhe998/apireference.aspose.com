---
title: Cell.Paragraphs
second_title: Référence de l'API Aspose.Words pour .NET
description: Cell propriété. Obtient une collection de paragraphes qui sont des enfants immédiats de la cellule.
type: docs
weight: 80
url: /fr/net/aspose.words.tables/cell/paragraphs/
---
## Cell.Paragraphs property

Obtient une collection de paragraphes qui sont des enfants immédiats de la cellule.

```csharp
public ParagraphCollection Paragraphs { get; }
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

* class [ParagraphCollection](../../../aspose.words/paragraphcollection/)
* class [Cell](../)
* espace de noms [Aspose.Words.Tables](../../cell/)
* Assemblée [Aspose.Words](../../../)


