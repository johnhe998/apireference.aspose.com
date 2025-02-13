---
title: ShapeBase.ScreenTip
second_title: Aspose.Words per .NET API Reference
description: ShapeBase proprietà. Definisce il testo visualizzato quando il puntatore del mouse si sposta sulla forma.
type: docs
weight: 440
url: /it/net/aspose.words.drawing/shapebase/screentip/
---
## ShapeBase.ScreenTip property

Definisce il testo visualizzato quando il puntatore del mouse si sposta sulla forma.

```csharp
public string ScreenTip { get; set; }
```

### Osservazioni

Il valore predefinito è una stringa vuota.

### Esempi

Mostra come inserire una forma che contiene un'immagine ed è anche un collegamento ipertestuale.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.HRef = "https://forum.aspose.com/";
shape.Target = "New Window";
shape.ScreenTip = "Aspose.Words Support Forums";

// Ctrl + clic sinistro sulla forma in Microsoft Word aprirà una nuova finestra del browser web
// e portaci al collegamento ipertestuale nella proprietà "HRef".
doc.Save(ArtifactsDir + "Image.InsertImageWithHyperlink.docx");
```

### Guarda anche

* class [ShapeBase](../)
* spazio dei nomi [Aspose.Words.Drawing](../../shapebase/)
* assemblea [Aspose.Words](../../../)


