---
title: Enum PdfImageCompression
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Saving.PdfImageCompression enum. Specifica il tipo di compressione applicato alle immagini nel file PDF.
type: docs
weight: 5210
url: /it/net/aspose.words.saving/pdfimagecompression/
---
## PdfImageCompression enumeration

Specifica il tipo di compressione applicato alle immagini nel file PDF.

```csharp
public enum PdfImageCompression
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| Auto | `0` | Seleziona automaticamente la compressione più appropriata per ogni immagine. |
| Jpeg | `1` | Compressione Jpeg. Non supporta la trasparenza. |

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

* spazio dei nomi [Aspose.Words.Saving](../../aspose.words.saving/)
* assemblea [Aspose.Words](../../)


