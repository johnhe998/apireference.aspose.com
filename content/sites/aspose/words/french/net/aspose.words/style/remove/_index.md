---
title: Style.Remove
second_title: Référence de l'API Aspose.Words pour .NET
description: Style méthode. Supprime le style spécifié du document.
type: docs
weight: 180
url: /fr/net/aspose.words/style/remove/
---
## Style.Remove method

Supprime le style spécifié du document.

```csharp
public void Remove()
```

### Remarques

La suppression du style a les effets suivants sur le modèle de document :

* Toutes les références au style sont supprimées des paragraphes, passages et tableaux correspondants.
* Si le style de base est supprimé, sa mise en forme est déplacée vers les styles enfants.
* Si le style à supprimer a un style lié, les deux sont supprimés.

### Exemples

Montre comment créer et appliquer un style personnalisé.

```csharp
Document doc = new Document();

Style style = doc.Styles.Add(StyleType.Paragraph, "MyStyle");
style.Font.Name = "Times New Roman";
style.Font.Size = 16;
style.Font.Color = Color.Navy;

DocumentBuilder builder = new DocumentBuilder(doc);

// Appliquez l'un des styles du document au paragraphe que le générateur de document est en train de créer.
builder.ParagraphFormat.Style = doc.Styles["MyStyle"];
builder.Writeln("Hello world!");

Style firstParagraphStyle = doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Style;

Assert.AreEqual(style, firstParagraphStyle);

// Supprime notre style personnalisé de la collection de styles du document.
doc.Styles["MyStyle"].Remove();

firstParagraphStyle = doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Style;

// Tout texte qui utilisait un style supprimé revient au formatage par défaut.
Assert.False(doc.Styles.Any(s => s.Name == "MyStyle"));
Assert.AreEqual("Times New Roman", firstParagraphStyle.Font.Name);
Assert.AreEqual(12.0d, firstParagraphStyle.Font.Size);
Assert.AreEqual(Color.Empty.ToArgb(), firstParagraphStyle.Font.Color.ToArgb());
```

### Voir également

* class [Style](../)
* espace de noms [Aspose.Words](../../style/)
* Assemblée [Aspose.Words](../../../)


