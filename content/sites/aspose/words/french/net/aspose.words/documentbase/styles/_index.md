---
title: DocumentBase.Styles
second_title: Référence de l'API Aspose.Words pour .NET
description: DocumentBase propriété. Renvoie une collection de styles définis dans le document.
type: docs
weight: 80
url: /fr/net/aspose.words/documentbase/styles/
---
## DocumentBase.Styles property

Renvoie une collection de styles définis dans le document.

```csharp
public StyleCollection Styles { get; }
```

### Remarques

Pour plus d'informations, consultez la description du[`StyleCollection`](../../stylecollection/) classer.

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

Montre comment créer et utiliser un style de paragraphe avec une mise en forme de liste.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crée un style de paragraphe personnalisé.
Style style = doc.Styles.Add(StyleType.Paragraph, "MyStyle1");
style.Font.Size = 24;
style.Font.Name = "Verdana";
style.ParagraphFormat.SpaceAfter = 12;

// Créez une liste et assurez-vous que les paragraphes qui utilisent ce style utiliseront cette liste.
style.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDefault);
style.ListFormat.ListLevelNumber = 0;

// Appliquez le style de paragraphe au paragraphe actuel du générateur de document, puis ajoutez du texte.
builder.ParagraphFormat.Style = style;
builder.Writeln("Hello World: MyStyle1, bulleted list.");

// Modifiez le style du générateur de document en un style qui n'a pas de formatage de liste et écrivez un autre paragraphe.
builder.ParagraphFormat.Style = doc.Styles["Normal"];
builder.Writeln("Hello World: Normal.");

builder.Document.Save(ArtifactsDir + "Styles.ParagraphStyleBulletedList.docx");
```

### Voir également

* class [StyleCollection](../../stylecollection/)
* class [DocumentBase](../)
* espace de noms [Aspose.Words](../../documentbase/)
* Assemblée [Aspose.Words](../../../)


