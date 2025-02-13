---
title: ShapeBase.RelativeVerticalPosition
second_title: Aspose.Words per .NET API Reference
description: ShapeBase proprietà. Specifica il posizionamento verticale della forma.
type: docs
weight: 410
url: /it/net/aspose.words.drawing/shapebase/relativeverticalposition/
---
## ShapeBase.RelativeVerticalPosition property

Specifica il posizionamento verticale della forma.

```csharp
public RelativeVerticalPosition RelativeVerticalPosition { get; set; }
```

### Osservazioni

Il valore predefinito èParagraph.

Ha effetto solo per le forme mobili di livello superiore.

### Esempi

Mostra come inserire un'immagine mobile al centro di una pagina.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserisci un'immagine mobile che apparirà dietro il testo sovrapposto e allineala al centro della pagina.
Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.WrapType = WrapType.None;
shape.BehindText = true;
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.HorizontalAlignment = HorizontalAlignment.Center;
shape.VerticalAlignment = VerticalAlignment.Center;

doc.Save(ArtifactsDir + "Image.CreateFloatingPageCenter.docx");
```

### Guarda anche

* enum [RelativeVerticalPosition](../../relativeverticalposition/)
* class [ShapeBase](../)
* spazio dei nomi [Aspose.Words.Drawing](../../shapebase/)
* assemblea [Aspose.Words](../../../)


