---
title: Enum PdfImageCompression
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Saving.PdfImageCompression enumeración. Especifica el tipo de compresión aplicada a las imágenes en el archivo PDF.
type: docs
weight: 5210
url: /es/net/aspose.words.saving/pdfimagecompression/
---
## PdfImageCompression enumeration

Especifica el tipo de compresión aplicada a las imágenes en el archivo PDF.

```csharp
public enum PdfImageCompression
```

### Valores

| Nombre | Valor | Descripción |
| --- | --- | --- |
| Auto | `0` | Selecciona automáticamente la compresión más adecuada para cada imagen. |
| Jpeg | `1` | Compresión jpeg. No admite transparencia. |

### Ejemplos

Muestra cómo especificar un tipo de compresión para todas las imágenes en un documento que estamos convirtiendo a PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Jpeg image:");
builder.InsertImage(ImageDir + "Logo.jpg");
builder.InsertParagraph();
builder.Writeln("Png image:");
builder.InsertImage(ImageDir + "Transparent background logo.png");

// Crea un objeto "PdfSaveOptions" que podemos pasar al método "Guardar" del documento
// para modificar cómo ese método convierte el documento a .PDF.
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();

// Establezca la propiedad "ImageCompression" en "PdfImageCompression.Auto" para usar el
// Propiedad "ImageCompression" para controlar la calidad de las imágenes Jpeg que terminan en el PDF de salida.
// Establezca la propiedad "ImageCompression" en "PdfImageCompression.Jpeg" para usar el
// Propiedad "ImageCompression" para controlar la calidad de todas las imágenes que terminan en el PDF de salida.
pdfSaveOptions.ImageCompression = pdfImageCompression;

// Establezca la propiedad "JpegQuality" en "10" para fortalecer la compresión a costa de la calidad de la imagen.
pdfSaveOptions.JpegQuality = 10;

doc.Save(ArtifactsDir + "PdfSaveOptions.ImageCompression.pdf", pdfSaveOptions);
```

### Ver también

* espacio de nombres [Aspose.Words.Saving](../../aspose.words.saving/)
* asamblea [Aspose.Words](../../)


