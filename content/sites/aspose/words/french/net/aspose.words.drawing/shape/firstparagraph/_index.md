---
title: Shape.FirstParagraph
second_title: Référence de l'API Aspose.Words pour .NET
description: Shape propriété. Récupère le premier paragraphe de la forme.
type: docs
weight: 60
url: /fr/net/aspose.words.drawing/shape/firstparagraph/
---
## Shape.FirstParagraph property

Récupère le premier paragraphe de la forme.

```csharp
public Paragraph FirstParagraph { get; }
```

### Exemples

Montre comment créer et mettre en forme une zone de texte.

```csharp
Document doc = new Document();

// Crée une zone de texte flottante.
Shape textBox = new Shape(doc, ShapeType.TextBox);
textBox.WrapType = WrapType.None;
textBox.Height = 50;
textBox.Width = 200;

// Définit l'alignement horizontal et vertical du texte à l'intérieur de la forme.
textBox.HorizontalAlignment = HorizontalAlignment.Center;
textBox.VerticalAlignment = VerticalAlignment.Top;

// Ajoute un paragraphe à la zone de texte et ajoute une suite de texte que la zone de texte affichera.
textBox.AppendChild(new Paragraph(doc));
Paragraph para = textBox.FirstParagraph;
para.ParagraphFormat.Alignment = ParagraphAlignment.Center;
Run run = new Run(doc);
run.Text = "Hello world!";
para.AppendChild(run);

doc.FirstSection.Body.FirstParagraph.AppendChild(textBox);

doc.Save(ArtifactsDir + "Shape.CreateTextBox.docx");
```

### Voir également

* class [Paragraph](../../../aspose.words/paragraph/)
* class [Shape](../)
* espace de noms [Aspose.Words.Drawing](../../shape/)
* Assemblée [Aspose.Words](../../../)


