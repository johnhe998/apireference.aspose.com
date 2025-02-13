---
title: Shape.TextBox
second_title: Référence de l'API Aspose.Words pour .NET
description: Shape propriété. Définit les attributs qui spécifient comment le texte est affiché dans une forme.
type: docs
weight: 220
url: /fr/net/aspose.words.drawing/shape/textbox/
---
## Shape.TextBox property

Définit les attributs qui spécifient comment le texte est affiché dans une forme.

```csharp
public TextBox TextBox { get; }
```

### Exemples

Montre comment définir l'orientation du texte dans une zone de texte.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape textBoxShape = builder.InsertShape(ShapeType.TextBox, 150, 100);
TextBox textBox = textBoxShape.TextBox;

// Déplacez le générateur de document à l'intérieur du TextBox et ajoutez du texte.
builder.MoveTo(textBoxShape.LastParagraph);
builder.Writeln("Hello world!");
builder.Write("Hello again!");

// Définissez la propriété "LayoutFlow" pour définir une orientation pour le contenu textuel de cette zone de texte.
textBox.LayoutFlow = layoutFlow;

doc.Save(ArtifactsDir + "Shape.TextBoxLayoutFlow.docx");
```

### Voir également

* class [TextBox](../../textbox/)
* class [Shape](../)
* espace de noms [Aspose.Words.Drawing](../../shape/)
* Assemblée [Aspose.Words](../../../)


