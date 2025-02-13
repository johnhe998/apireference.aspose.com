---
title: ShapeBase.Top
second_title: Aspose.Words per .NET API Reference
description: ShapeBase proprietà. Ottiene o imposta la posizione del bordo superiore del blocco contenitore della forma.
type: docs
weight: 500
url: /it/net/aspose.words.drawing/shapebase/top/
---
## ShapeBase.Top property

Ottiene o imposta la posizione del bordo superiore del blocco contenitore della forma.

```csharp
public double Top { get; set; }
```

### Osservazioni

Per una forma di livello superiore, il valore è in punti e relativo all'ancoraggio della forma.

Per le forme in un gruppo, il valore è nello spazio delle coordinate e nelle unità del gruppo padre.

Il valore predefinito è 0.

Ha effetto solo per le forme fluttuanti.

### Esempi

Mostra come inserire un'immagine mobile e specificarne la posizione e le dimensioni.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.WrapType = WrapType.None;

// Configura la proprietà "RelativeHorizontalPosition" della forma per trattare il valore della proprietà "Left"
 // come distanza orizzontale della forma, in punti, dal lato sinistro della pagina.
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;

// Imposta la distanza orizzontale della forma dal lato sinistro della pagina su 100.
shape.Left = 100;

// Usa la proprietà "RelativeVerticalPosition" in modo simile per posizionare la forma 80pt sotto la parte superiore della pagina.
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.Top = 80;

// Imposta l'altezza della forma, che ridimensionerà automaticamente la larghezza per preservare le dimensioni.
shape.Height = 125;

Assert.AreEqual(125.0d, shape.Width);

// Le proprietà "Bottom" e "Right" contengono i bordi inferiore e destro dell'immagine.
Assert.AreEqual(shape.Top + shape.Height, shape.Bottom);
Assert.AreEqual(shape.Left + shape.Width, shape.Right);

doc.Save(ArtifactsDir + "Image.CreateFloatingPositionSize.docx");
```

### Guarda anche

* class [ShapeBase](../)
* spazio dei nomi [Aspose.Words.Drawing](../../shapebase/)
* assemblea [Aspose.Words](../../../)


