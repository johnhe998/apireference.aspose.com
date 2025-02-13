---
title: Shape.TextBox
second_title: Aspose.Words för .NET API Referens
description: Shape fast egendom. Definierar attribut som anger hur text visas i en form.
type: docs
weight: 220
url: /sv/net/aspose.words.drawing/shape/textbox/
---
## Shape.TextBox property

Definierar attribut som anger hur text visas i en form.

```csharp
public TextBox TextBox { get; }
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

* class [TextBox](../../textbox/)
* class [Shape](../)
* namnutrymme [Aspose.Words.Drawing](../../shape/)
* hopsättning [Aspose.Words](../../../)


