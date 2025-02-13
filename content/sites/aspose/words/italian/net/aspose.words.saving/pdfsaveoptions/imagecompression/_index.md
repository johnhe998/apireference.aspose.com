---
title: PdfSaveOptions.ImageCompression
second_title: Aspose.Words per .NET API Reference
description: PdfSaveOptions proprietà. Specifica il tipo di compressione da utilizzare per tutte le immagini nel documento.
type: docs
weight: 170
url: /it/net/aspose.words.saving/pdfsaveoptions/imagecompression/
---
## PdfSaveOptions.ImageCompression property

Specifica il tipo di compressione da utilizzare per tutte le immagini nel documento.

```csharp
public PdfImageCompression ImageCompression { get; set; }
```

### Osservazioni

L'impostazione predefinita èAuto.

UsandoJpeg consente di controllare la qualità delle immagini nel documento di output tramite il[`JpegQuality`](../jpegquality/) proprietà.

UsandoJpeg fornisce la velocità di conversione più elevata rispetto alle prestazioni di altri tipi di compressione, ma in questo caso è presente una compressione JPEG con perdita.

UsandoAuto consente di controllare la qualità di Jpeg nel documento di output tramite il[`JpegQuality`](../jpegquality/) proprietà, ma per altri formati, i dati dei pixel grezzi vengono estratti e salvati con la compressione Flate. Questo caso è più lento della conversione Jpeg ma senza perdite.

### Esempi

Mostra come specificare un tipo di compressione per tutte le immagini in un documento che stiamo convertendo in PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Jpeg image:");
builder.InsertImage(ImageDir + "Logo.jpg");
builder.InsertParagraph();
builder.Writeln("Png image:");
builder.InsertImage(ImageDir + "Transparent background logo.png");

// Crea un oggetto "PdfSaveOptions" che possiamo passare al metodo "Save" del documento
// per modificare il modo in cui quel metodo converte il documento in .PDF.
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();

// Imposta la proprietà "ImageCompression" su "PdfImageCompression.Auto" per utilizzare il file
// Proprietà "ImageCompression" per controllare la qualità delle immagini Jpeg che finiscono nel PDF di output.
// Imposta la proprietà "ImageCompression" su "PdfImageCompression.Jpeg" per usare il file
// Proprietà "ImageCompression" per controllare la qualità di tutte le immagini che finiscono nel PDF di output.
pdfSaveOptions.ImageCompression = pdfImageCompression;

// Imposta la proprietà "JpegQuality" su "10" per rafforzare la compressione a scapito della qualità dell'immagine.
pdfSaveOptions.JpegQuality = 10;

doc.Save(ArtifactsDir + "PdfSaveOptions.ImageCompression.pdf", pdfSaveOptions);
```

### Guarda anche

* enum [PdfImageCompression](../../pdfimagecompression/)
* class [PdfSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../pdfsaveoptions/)
* assemblea [Aspose.Words](../../../)


