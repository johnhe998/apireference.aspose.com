---
title: StyleCollection.Add
second_title: Référence de l'API Aspose.Words pour .NET
description: StyleCollection méthode. Crée un nouveau style défini par lutilisateur et lajoute à la collection.
type: docs
weight: 60
url: /fr/net/aspose.words/stylecollection/add/
---
## StyleCollection.Add method

Crée un nouveau style défini par l'utilisateur et l'ajoute à la collection.

```csharp
public Style Add(StyleType type, string name)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| type | StyleType | UN[`StyleType`](../../styletype/) valeur qui spécifie le type de style à créer. |
| name | String | Nom sensible à la casse du style à créer. |

### Remarques

Vous pouvez créer un style de caractère, de paragraphe ou de liste.

Lors de la création d'un style de liste, le style est créé avec le formatage de liste numérotée par défaut (1 \ a \ i).

Lève une exception si un style portant ce nom existe déjà.

### Exemples

Montre comment ajouter un style à la collection de styles d'un document.

```csharp
Document doc = new Document();
StyleCollection styles = doc.Styles;

// Définissez les paramètres par défaut pour les nouveaux styles que nous pourrons ajouter ultérieurement à cette collection.
styles.DefaultFont.Name = "Courier New";

// Si nous ajoutons un style du "StyleType.Paragraph", la collection appliquera les valeurs de
// sa propriété "DefaultParagraphFormat" à la propriété "ParagraphFormat" du style.
styles.DefaultParagraphFormat.FirstLineIndent = 15.0;

// Ajoutez un style, puis vérifiez qu'il possède les paramètres par défaut.
styles.Add(StyleType.Paragraph, "MyStyle");

Assert.AreEqual("Courier New", styles[4].Font.Name);
Assert.AreEqual(15.0, styles["MyStyle"].ParagraphFormat.FirstLineIndent);
```

Montre comment créer un style de liste et l'utiliser dans un document.

```csharp
Document doc = new Document();

// Une liste nous permet d'organiser et de décorer des ensembles de paragraphes avec des symboles de préfixe et des retraits.
// Nous pouvons créer des listes imbriquées en augmentant le niveau d'indentation. 
// Nous pouvons commencer et terminer une liste en utilisant la propriété "ListFormat" d'un générateur de document. 
// Chaque paragraphe que nous ajoutons entre le début et la fin d'une liste deviendra un élément de la liste.
// Nous pouvons contenir un objet List entier dans un style.
Style listStyle = doc.Styles.Add(StyleType.List, "MyListStyle");

List list1 = listStyle.List;

Assert.True(list1.IsListStyleDefinition);
Assert.False(list1.IsListStyleReference);
Assert.True(list1.IsMultiLevel);
Assert.AreEqual(listStyle, list1.Style);

// Modifie l'apparence de tous les niveaux de liste dans notre liste.
foreach (ListLevel level in list1.ListLevels)
{
    level.Font.Name = "Verdana";
    level.Font.Color = Color.Blue;
    level.Font.Bold = true;
}

DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Using list style first time:");

// Crée une autre liste à partir d'une liste dans un style.
List list2 = doc.Lists.Add(listStyle);

Assert.False(list2.IsListStyleDefinition);
Assert.True(list2.IsListStyleReference);
Assert.AreEqual(listStyle, list2.Style);

// Ajoutez des éléments de liste que notre liste formatera.
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Writeln("Using list style second time:");

// Crée et applique une autre liste basée sur le style de liste.
List list3 = doc.Lists.Add(listStyle);
builder.ListFormat.List = list3;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(ArtifactsDir + "Lists.CreateAndUseListStyle.docx");
```

### Voir également

* class [Style](../../style/)
* enum [StyleType](../../styletype/)
* class [StyleCollection](../)
* espace de noms [Aspose.Words](../../stylecollection/)
* Assemblée [Aspose.Words](../../../)


