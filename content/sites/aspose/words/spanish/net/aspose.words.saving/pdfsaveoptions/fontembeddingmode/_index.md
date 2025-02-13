---
title: PdfSaveOptions.FontEmbeddingMode
second_title: Referencia de API de Aspose.Words para .NET
description: PdfSaveOptions propiedad. Especifica el modo de incrustación de fuentes.
type: docs
weight: 140
url: /es/net/aspose.words.saving/pdfsaveoptions/fontembeddingmode/
---
## PdfSaveOptions.FontEmbeddingMode property

Especifica el modo de incrustación de fuentes.

```csharp
public PdfFontEmbeddingMode FontEmbeddingMode { get; set; }
```

### Observaciones

El valor predeterminado esEmbedAll.

Esta configuración solo funciona para el texto en codificación ANSI (Windows-1252). Si el documento contiene texto no ANSI, las fuentes correspondientes se incrustarán independientemente de esta configuración.

El cumplimiento de PDF/A y PDF/UA requiere que se incrusten todas las fuentes. EmbedAll El valor se utilizará automáticamente al guardar en PDF/A y PDF/UA.

### Ejemplos

Muestra cómo configurar Aspose.Words para omitir la incrustación de fuentes Arial y Times New Roman en un documento PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// "Arial" es una fuente estándar y "Courier New" es una fuente no estándar.
builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Courier New";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

// Crea un objeto "PdfSaveOptions" que podemos pasar al método "Guardar" del documento
// para modificar cómo ese método convierte el documento a .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Establezca la propiedad "EmbedFullFonts" en "true" para incrustar cada glifo de cada fuente incrustada en el PDF de salida.
options.EmbedFullFonts = true;

// Establezca la propiedad "FontEmbeddingMode" en "EmbedAll" para incrustar todas las fuentes en el PDF de salida.
// Establezca la propiedad "FontEmbeddingMode" en "EmbedNonstandard" para permitir solo la incrustación de fuentes no estándar en el PDF de salida.
// Establezca la propiedad "FontEmbeddingMode" en "EmbedNone" para no incrustar ninguna fuente en el PDF de salida.
options.FontEmbeddingMode = pdfFontEmbeddingMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.EmbedWindowsFonts.pdf", options);

switch (pdfFontEmbeddingMode)
{
    case PdfFontEmbeddingMode.EmbedAll:
        Assert.That(1000000, Is.LessThan(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedWindowsFonts.pdf").Length));
        break;
    case PdfFontEmbeddingMode.EmbedNonstandard:
        Assert.That(480000, Is.LessThan(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedWindowsFonts.pdf").Length));
        break;
    case PdfFontEmbeddingMode.EmbedNone:
        Assert.That(4217, Is.AtLeast(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedWindowsFonts.pdf").Length));
        break;
}
```

### Ver también

* enum [PdfFontEmbeddingMode](../../pdffontembeddingmode/)
* class [PdfSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../pdfsaveoptions/)
* asamblea [Aspose.Words](../../../)


