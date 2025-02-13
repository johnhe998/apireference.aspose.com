---
title: ListLabel.LabelValue
second_title: Référence de l'API Aspose.Words pour .NET
description: ListLabel propriété. Obtient une valeur numérique pour cette étiquette.
type: docs
weight: 30
url: /fr/net/aspose.words.lists/listlabel/labelvalue/
---
## ListLabel.LabelValue property

Obtient une valeur numérique pour cette étiquette.

```csharp
public int LabelValue { get; }
```

### Remarques

Utilisez le[`UpdateListLabels`](../../../aspose.words/document/updatelistlabels/) méthode pour mettre à jour la valeur de cette propriété.

### Exemples

Montre comment extraire les étiquettes de liste de tous les paragraphes qui sont des éléments de liste.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");
doc.UpdateListLabels();

NodeCollection paras = doc.GetChildNodes(NodeType.Paragraph, true);

// Recherche si nous avons la liste des paragraphes. Dans notre document, notre liste utilise des chiffres arabes simples,
// qui commence à trois et se termine à six.
foreach (Paragraph paragraph in paras.OfType<Paragraph>().Where(p => p.ListFormat.IsListItem))
{
    Console.WriteLine($"List item paragraph #{paras.IndexOf(paragraph)}");

    // C'est le texte que nous obtenons lorsque nous obtenons ce nœud au format texte.
    // Cette sortie de texte omettra les étiquettes de liste. Coupez tous les caractères de formatage de paragraphe. 
    string paragraphText = paragraph.ToString(SaveFormat.Text).Trim();
    Console.WriteLine($"\tExported Text: {paragraphText}");

    ListLabel label = paragraph.ListLabel;

    // Cela obtient la position du paragraphe dans le niveau actuel de la liste. Si nous avons une liste à plusieurs niveaux,
    // cela nous dira quelle position il est à ce niveau.
    Console.WriteLine($"\tNumerical Id: {label.LabelValue}");

    // Combinez-les pour inclure l'étiquette de la liste avec le texte dans la sortie.
    Console.WriteLine($"\tList label combined with text: {label.LabelString} {paragraphText}");
}
```

### Voir également

* class [ListLabel](../)
* espace de noms [Aspose.Words.Lists](../../listlabel/)
* Assemblée [Aspose.Words](../../../)


