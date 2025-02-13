---
title: Shape.LastParagraph
second_title: Aspose.Words för .NET API Referens
description: Shape fast egendom. Får det sista stycket i formen.
type: docs
weight: 120
url: /sv/net/aspose.words.drawing/shape/lastparagraph/
---
## Shape.LastParagraph property

Får det sista stycket i formen.

```csharp
public Paragraph LastParagraph { get; }
```

### Exempel

Visar hur man ställer in orienteringen för text inuti en textruta.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape textBoxShape = builder.InsertShape(ShapeType.TextBox, 150, 100);
TextBox textBox = textBoxShape.TextBox;

// Flytta dokumentbyggaren till inuti TextBox och lägg till text.
builder.MoveTo(textBoxShape.LastParagraph);
builder.Writeln("Hello world!");
builder.Write("Hello again!");

// Ställ in egenskapen "LayoutFlow" för att ställa in en orientering för textinnehållet i denna textruta.
textBox.LayoutFlow = layoutFlow;

doc.Save(ArtifactsDir + "Shape.TextBoxLayoutFlow.docx");
```

### Se även

* class [Paragraph](../../../aspose.words/paragraph/)
* class [Shape](../)
* namnutrymme [Aspose.Words.Drawing](../../shape/)
* hopsättning [Aspose.Words](../../../)


