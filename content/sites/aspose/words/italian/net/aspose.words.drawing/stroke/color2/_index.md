---
title: Stroke.Color2
second_title: Aspose.Words per .NET API Reference
description: Stroke proprietà. Definisce un secondo colore per un tratto.
type: docs
weight: 30
url: /it/net/aspose.words.drawing/stroke/color2/
---
## Stroke.Color2 property

Definisce un secondo colore per un tratto.

```csharp
public Color Color2 { get; set; }
```

### Osservazioni

Il valore predefinito per a[`Shape`](../../shape/) è White.

### Esempi

Mostra come elaborare le caratteristiche del tratto di forma.

```csharp
Document doc = new Document(MyDir + "Shape stroke pattern border.docx");
Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);
Stroke stroke = shape.Stroke;

// I tratti possono avere due colori, che vengono utilizzati per creare un motivo definito dai dati dell'immagine a due tonalità.
// I tratti con un singolo colore non utilizzano la proprietà Color2.
Assert.AreEqual(Color.FromArgb(255, 128, 0, 0), stroke.Color);
Assert.AreEqual(Color.FromArgb(255, 255, 255, 0), stroke.Color2);

Assert.NotNull(stroke.ImageBytes);
File.WriteAllBytes(ArtifactsDir + "Drawing.StrokePattern.png", stroke.ImageBytes);
```

### Guarda anche

* class [Stroke](../)
* spazio dei nomi [Aspose.Words.Drawing](../../stroke/)
* assemblea [Aspose.Words](../../../)


