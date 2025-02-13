---
title: ImageData.ImageSize
second_title: Aspose.Words per .NET API Reference
description: ImageData proprietà. Ottiene le informazioni sulla dimensione e la risoluzione dellimmagine.
type: docs
weight: 130
url: /it/net/aspose.words.drawing/imagedata/imagesize/
---
## ImageData.ImageSize property

Ottiene le informazioni sulla dimensione e la risoluzione dell'immagine.

```csharp
public ImageSize ImageSize { get; }
```

### Osservazioni

Se l'immagine è solo collegata e non è memorizzata nel documento, restituisce dimensione zero.

### Esempi

Mostra come ridimensionare una forma con un'immagine.

```csharp
#if NET48 || JAVA
            Image image = Image.FromFile(ImageDir + "Logo.jpg");

            Assert.AreEqual(400, image.Size.Width);
            Assert.AreEqual(400, image.Size.Height);
#elif NET5_0_OR_GREATER
            SKBitmap image = SKBitmap.Decode(ImageDir + "Logo.jpg");

            Assert.AreEqual(400, image.Width);
            Assert.AreEqual(400, image.Height);
#endif

            // Quando inseriamo un'immagine utilizzando il metodo "InsertImage", il builder ridimensiona la forma che mostra l'immagine in modo che,
            // quando visualizziamo il documento utilizzando lo zoom del 100% in Microsoft Word, la forma mostra l'immagine nella sua dimensione effettiva.
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");

            // Un'immagine 400x400 creerà un oggetto ImageData con una dimensione dell'immagine di 300x300pt.
            ImageSize imageSize = shape.ImageData.ImageSize;

            Assert.AreEqual(300.0d, imageSize.WidthPoints);
            Assert.AreEqual(300.0d, imageSize.HeightPoints);

            // Se le dimensioni di una forma corrispondono alle dimensioni dei dati dell'immagine,
            // quindi la forma mostra l'immagine nella sua dimensione originale.
            Assert.AreEqual(300.0d, shape.Width);
            Assert.AreEqual(300.0d, shape.Height);

             // Riduci le dimensioni complessive della forma del 50%.
            shape.Width *= 0.5;

             // I fattori di ridimensionamento si applicano sia alla larghezza che all'altezza contemporaneamente per preservare le proporzioni della forma.
            Assert.AreEqual(150.0d, shape.Width);
            Assert.AreEqual(150.0d, shape.Height);

            // Quando ridimensioniamo la forma, la dimensione dei dati dell'immagine rimane la stessa.
            Assert.AreEqual(300.0d, imageSize.WidthPoints);
            Assert.AreEqual(300.0d, imageSize.HeightPoints);

            // Possiamo fare riferimento alle dimensioni dei dati dell'immagine per applicare un ridimensionamento in base alle dimensioni dell'immagine.
            shape.Width = imageSize.WidthPoints * 1.1;

            Assert.AreEqual(330.0d, shape.Width);
            Assert.AreEqual(330.0d, shape.Height);

            doc.Save(ArtifactsDir + "Image.ScaleImage.docx");
```

### Guarda anche

* class [ImageSize](../../imagesize/)
* class [ImageData](../)
* spazio dei nomi [Aspose.Words.Drawing](../../imagedata/)
* assemblea [Aspose.Words](../../../)


