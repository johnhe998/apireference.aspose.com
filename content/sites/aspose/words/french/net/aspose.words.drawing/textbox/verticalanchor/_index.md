---
title: TextBox.VerticalAnchor
second_title: Référence de l'API Aspose.Words pour .NET
description: TextBox propriété. Spécifie lalignement vertical du texte dans une forme.
type: docs
weight: 110
url: /fr/net/aspose.words.drawing/textbox/verticalanchor/
---
## TextBox.VerticalAnchor property

Spécifie l'alignement vertical du texte dans une forme.

```csharp
public TextBoxAnchor VerticalAnchor { get; set; }
```

### Remarques

La valeur par défaut estTop.

### Exemples

Montre comment aligner verticalement le contenu du texte d'une zone de texte.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.TextBox, 200, 200);

// Définissez la propriété "VerticalAnchor" sur "TextBoxAnchor.Top" pour
// aligne le texte de cette zone de texte avec le côté supérieur de la forme.
// Définissez la propriété "VerticalAnchor" sur "TextBoxAnchor.Middle" pour
// aligne le texte de cette zone de texte sur le centre de la forme.
// Définissez la propriété "VerticalAnchor" sur "TextBoxAnchor.Bottom" pour
// aligne le texte de cette zone de texte sur le bas de la forme.
shape.TextBox.VerticalAnchor = verticalAnchor;

builder.MoveTo(shape.FirstParagraph);
builder.Write("Hello world!");

// L'alignement vertical du texte à l'intérieur des zones de texte est disponible à partir de Microsoft Word 2007.
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2007);
doc.Save(ArtifactsDir + "Shape.VerticalAnchor.docx");
```

### Voir également

* enum [TextBoxAnchor](../../textboxanchor/)
* class [TextBox](../)
* espace de noms [Aspose.Words.Drawing](../../textbox/)
* Assemblée [Aspose.Words](../../../)


