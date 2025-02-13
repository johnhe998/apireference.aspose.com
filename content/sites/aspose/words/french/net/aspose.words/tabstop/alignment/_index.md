---
title: TabStop.Alignment
second_title: Référence de l'API Aspose.Words pour .NET
description: TabStop propriété. Obtient ou définit lalignement du texte à ce taquet de tabulation.
type: docs
weight: 20
url: /fr/net/aspose.words/tabstop/alignment/
---
## TabStop.Alignment property

Obtient ou définit l'alignement du texte à ce taquet de tabulation.

```csharp
public TabAlignment Alignment { get; set; }
```

### Exemples

Montre comment modifier la position du taquet de tabulation droit dans les paragraphes liés à la table des matières.

```csharp
Document doc = new Document(MyDir + "Table of contents.docx");

// Parcourt tous les paragraphes avec des styles basés sur les résultats TOC ; c'est n'importe quel style entre TOC et TOC9.
foreach (Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true).OfType<Paragraph>())
    if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
        para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
    {
        // Récupère le premier onglet utilisé dans ce paragraphe, ce devrait être l'onglet utilisé pour aligner les numéros de page.
        TabStop tab = para.ParagraphFormat.TabStops[0];

        // Remplace la première tabulation par défaut, stop par une tabulation personnalisée.
        para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
        para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
    }

doc.Save(ArtifactsDir + "Styles.ChangeTocsTabStops.docx");
```

### Voir également

* enum [TabAlignment](../../tabalignment/)
* class [TabStop](../)
* espace de noms [Aspose.Words](../../tabstop/)
* Assemblée [Aspose.Words](../../../)


