---
title: TextBox.FitShapeToText
second_title: Aspose.Words per .NET API Reference
description: TextBox proprietà. Determina se Microsoft Word aumenterà la forma per adattarla al testo.
type: docs
weight: 10
url: /it/net/aspose.words.drawing/textbox/fitshapetotext/
---
## TextBox.FitShapeToText property

Determina se Microsoft Word aumenterà la forma per adattarla al testo.

```csharp
public bool FitShapeToText { get; set; }
```

### Osservazioni

Il valore predefinito è **falso**.

### Esempi

Mostra come fare in modo che una casella di testo si ridimensioni per adattarla perfettamente al suo contenuto.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape textBoxShape = builder.InsertShape(ShapeType.TextBox, 150, 100);
TextBox textBox = textBoxShape.TextBox;

// Applica questi valori a entrambi questi membri per adattare la forma padre
// strettamente attorno al contenuto del testo, ignorando le dimensioni che abbiamo impostato.
textBox.FitShapeToText = true;
textBox.TextBoxWrapMode = TextBoxWrapMode.None;

builder.MoveTo(textBoxShape.LastParagraph);
builder.Write("Text fit tightly inside textbox.");

doc.Save(ArtifactsDir + "Shape.TextBoxFitShapeToText.docx");
```

### Guarda anche

* class [TextBox](../)
* spazio dei nomi [Aspose.Words.Drawing](../../textbox/)
* assemblea [Aspose.Words](../../../)


