---
title: Fill.Opacity
second_title: Aspose.Words per .NET API Reference
description: Fill proprietà. Ottiene o imposta il grado di opacità del riempimento specificato come un valore compreso tra 00 trasparente e 10 opaco.
type: docs
weight: 90
url: /it/net/aspose.words.drawing/fill/opacity/
---
## Fill.Opacity property

Ottiene o imposta il grado di opacità del riempimento specificato come un valore compreso tra 0,0 (trasparente) e 1,0 (opaco).

```csharp
public double Opacity { get; set; }
```

### Osservazioni

Questa proprietà è l'opposto della proprietà[`Transparency`](../transparency/).

### Esempi

Mostra come riempire una forma con un colore solido.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Scrivi del testo e poi coprilo con una forma fluttuante.
builder.Font.Size = 32;
builder.Writeln("Hello world!");

Shape shape = builder.InsertShape(ShapeType.CloudCallout, RelativeHorizontalPosition.LeftMargin, 25,
    RelativeVerticalPosition.TopMargin, 25, 250, 150, WrapType.None);

// Usa la proprietà "StrokeColor" per impostare il colore del contorno della forma.
shape.StrokeColor = Color.CadetBlue;

// Usa la proprietà "FillColor" per impostare il colore dell'area interna della forma.
shape.FillColor = Color.LightBlue;

// La proprietà "Opacità" determina la trasparenza del colore su una scala 0-1,
// con 1 completamente opaco e 0 invisibile.
// Il riempimento della forma per impostazione predefinita è completamente opaco, quindi non possiamo vedere il testo su cui si trova questa forma.
Assert.AreEqual(1.0d, shape.Fill.Opacity);

// Imposta l'opacità del colore di riempimento della forma su un valore inferiore in modo da poter vedere il testo sottostante.
shape.Fill.Opacity = 0.3;

doc.Save(ArtifactsDir + "Shape.Fill.docx");
```

### Guarda anche

* class [Fill](../)
* spazio dei nomi [Aspose.Words.Drawing](../../fill/)
* assemblea [Aspose.Words](../../../)


