---
title: FixedPageSaveOptions.JpegQuality
second_title: Aspose.Words per .NET API Reference
description: FixedPageSaveOptions proprietà. Ottiene o imposta un valore che determina la qualità delle immagini JPEG allinterno del documento Html.
type: docs
weight: 20
url: /it/net/aspose.words.saving/fixedpagesaveoptions/jpegquality/
---
## FixedPageSaveOptions.JpegQuality property

Ottiene o imposta un valore che determina la qualità delle immagini JPEG all'interno del documento Html.

```csharp
public int JpegQuality { get; set; }
```

### Osservazioni

Ha effetto solo quando un documento contiene immagini JPEG.

Utilizzare questa proprietà per ottenere o impostare la qualità delle immagini all'interno di un documento durante il salvataggio in formato pagina fisso. Il valore può variare da 0 a 100 dove 0 indica la qualità peggiore ma la compressione massima e 100 indica la qualità migliore ma la compressione minima.

Il valore predefinito è 95.

### Esempi

Mostra come configurare la compressione durante il salvataggio di un documento come JPEG.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertImage(ImageDir + "Logo.jpg");

// Crea un oggetto "ImageSaveOptions" che possiamo passare al metodo "Salva" del documento
// per modificare il modo in cui quel metodo esegue il rendering del documento in un'immagine.
ImageSaveOptions imageOptions = new ImageSaveOptions(SaveFormat.Jpeg);

// Imposta la proprietà "JpegQuality" su "10" per utilizzare una compressione più forte durante il rendering del documento.
// Ciò ridurrà le dimensioni del file del documento, ma l'immagine mostrerà artefatti di compressione più evidenti.
imageOptions.JpegQuality = 10;

doc.Save(ArtifactsDir + "ImageSaveOptions.JpegQuality.HighCompression.jpg", imageOptions);

Assert.That(20000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.JpegQuality.HighCompression.jpg").Length));

// Imposta la proprietà "JpegQuality" su "100" per utilizzare una compressione più debole durante il rendering del documento.
// Ciò migliorerà la qualità dell'immagine al costo di una maggiore dimensione del file.
imageOptions.JpegQuality = 100;

doc.Save(ArtifactsDir + "ImageSaveOptions.JpegQuality.HighQuality.jpg", imageOptions);

Assert.That(60000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.JpegQuality.HighQuality.jpg").Length));
```

### Guarda anche

* class [FixedPageSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../fixedpagesaveoptions/)
* assemblea [Aspose.Words](../../../)


