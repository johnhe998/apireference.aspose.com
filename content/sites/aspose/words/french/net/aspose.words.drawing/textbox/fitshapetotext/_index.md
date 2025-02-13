---
title: TextBox.FitShapeToText
second_title: Référence de l'API Aspose.Words pour .NET
description: TextBox propriété. Détermine si Microsoft Word agrandit la forme pour ladapter au texte.
type: docs
weight: 10
url: /fr/net/aspose.words.drawing/textbox/fitshapetotext/
---
## TextBox.FitShapeToText property

Détermine si Microsoft Word agrandit la forme pour l'adapter au texte.

```csharp
public bool FitShapeToText { get; set; }
```

### Remarques

La valeur par défaut est **faux**.

### Exemples

Montre comment faire en sorte qu'une zone de texte se redimensionne pour s'adapter parfaitement à son contenu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape textBoxShape = builder.InsertShape(ShapeType.TextBox, 150, 100);
TextBox textBox = textBoxShape.TextBox;

// Appliquez ces valeurs à ces deux membres pour que la forme parent s'adapte
// étroitement autour du contenu du texte, en ignorant les dimensions que nous avons définies.
textBox.FitShapeToText = true;
textBox.TextBoxWrapMode = TextBoxWrapMode.None;

builder.MoveTo(textBoxShape.LastParagraph);
builder.Write("Text fit tightly inside textbox.");

doc.Save(ArtifactsDir + "Shape.TextBoxFitShapeToText.docx");
```

### Voir également

* class [TextBox](../)
* espace de noms [Aspose.Words.Drawing](../../textbox/)
* Assemblée [Aspose.Words](../../../)


