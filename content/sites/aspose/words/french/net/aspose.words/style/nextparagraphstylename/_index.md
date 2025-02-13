---
title: Style.NextParagraphStyleName
second_title: Référence de l'API Aspose.Words pour .NET
description: Style propriété. Obtient/définit le nom du style à appliquer automatiquement à un nouveau paragraphe inséré après un paragraphe formaté avec le style spécifié.
type: docs
weight: 120
url: /fr/net/aspose.words/style/nextparagraphstylename/
---
## Style.NextParagraphStyleName property

Obtient/définit le nom du style à appliquer automatiquement à un nouveau paragraphe inséré après un paragraphe formaté avec le style spécifié.

```csharp
public string NextParagraphStyleName { get; set; }
```

### Remarques

Cette propriété n'est pas utilisée par Aspose.Words. Le style de paragraphe suivant ne sera appliqué automatiquement que lorsque vous modifierez le document dans MS Word.

### Exemples

Montre comment accéder à la collection de styles d'un document.

```csharp
Document doc = new Document();

Assert.AreEqual(4, doc.Styles.Count);

// Énumère et liste tous les styles qu'un document créé avec Aspose.Words contient par défaut.
using (IEnumerator<Style> stylesEnum = doc.Styles.GetEnumerator())
{
    while (stylesEnum.MoveNext())
    {
        Style curStyle = stylesEnum.Current;
        Console.WriteLine($"Style name:\t\"{curStyle.Name}\", of type \"{curStyle.Type}\"");
        Console.WriteLine($"\tSubsequent style:\t{curStyle.NextParagraphStyleName}");
        Console.WriteLine($"\tIs heading:\t\t\t{curStyle.IsHeading}");
        Console.WriteLine($"\tIs QuickStyle:\t\t{curStyle.IsQuickStyle}");

        Assert.AreEqual(doc, curStyle.Document);
    }
}
```

### Voir également

* class [Style](../)
* espace de noms [Aspose.Words](../../style/)
* Assemblée [Aspose.Words](../../../)


