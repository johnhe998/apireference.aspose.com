---
title: Class TabStop
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.TabStop classe. Représente un seul taquet de tabulation personnalisé. La TabStop lobjet est membre de the TabStopCollection collection.
type: docs
weight: 5900
url: /fr/net/aspose.words/tabstop/
---
## TabStop class

Représente un seul taquet de tabulation personnalisé. La **TabStop** l'objet est membre de the [`TabStopCollection`](../tabstopcollection/) collection.

```csharp
public sealed class TabStop
```

## Constructeurs

| Nom | La description |
| --- | --- |
| [TabStop](tabstop/#constructor)(double) | Initialise une nouvelle instance de cette classe. |
| [TabStop](tabstop/#constructor_1)(double, TabAlignment, TabLeader) | Initialise une nouvelle instance de cette classe. |

## Propriétés

| Nom | La description |
| --- | --- |
| [Alignment](../../aspose.words/tabstop/alignment/) { get; set; } | Obtient ou définit l'alignement du texte à ce taquet de tabulation. |
| [IsClear](../../aspose.words/tabstop/isclear/) { get; } | Renvoie vrai si ce taquet de tabulation efface tous les taquets de tabulation existants à cette position. |
| [Leader](../../aspose.words/tabstop/leader/) { get; set; } | Obtient ou définit le type de la ligne de repère affichée sous le caractère de tabulation. |
| [Position](../../aspose.words/tabstop/position/) { get; } | Obtient la position du taquet de tabulation en points. |

## Méthodes

| Nom | La description |
| --- | --- |
| [Equals](../../aspose.words/tabstop/equals/#equals)(TabStop) | Compare avec le TabStop spécifié. |
| override [GetHashCode](../../aspose.words/tabstop/gethashcode/)() | Calcule le code de hachage pour cet objet. |

### Remarques

Normalement, un taquet de tabulation spécifie une position où un taquet de tabulation existe. Mais comme les taquets de tabulation peuvent être hérités des styles parents, il peut être nécessaire que l'objet enfant définisse explicitement qu'il n'y a pas de taquet de tabulation à une position donnée. Pour effacer un taquet de tabulation hérité à une position donnée, créez un **TabStop** objet et set [`Alignment`](./alignment/) à`TabAlignment.Clear`.

Pour plus d'informations, voir[`TabStopCollection`](../tabstopcollection/).

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

* espace de noms [Aspose.Words](../../aspose.words/)
* Assemblée [Aspose.Words](../../)


