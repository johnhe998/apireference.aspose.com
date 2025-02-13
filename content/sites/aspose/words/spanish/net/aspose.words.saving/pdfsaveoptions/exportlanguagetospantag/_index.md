---
title: PdfSaveOptions.ExportLanguageToSpanTag
second_title: Referencia de API de Aspose.Words para .NET
description: PdfSaveOptions propiedad. Obtiene o establece un valor que determina si se crea o no una etiqueta Span en la estructura del documento para exportar el idioma del texto.
type: docs
weight: 130
url: /es/net/aspose.words.saving/pdfsaveoptions/exportlanguagetospantag/
---
## PdfSaveOptions.ExportLanguageToSpanTag property

Obtiene o establece un valor que determina si se crea o no una etiqueta "Span" en la estructura del documento para exportar el idioma del texto.

```csharp
public bool ExportLanguageToSpanTag { get; set; }
```

### Observaciones

El valor predeterminado es`falso` y el atributo "Lang" se adjunta a una secuencia de contenido marcado en un flujo de contenido de página.

Cuando el valor es`verdadero` La etiqueta "Span" se crea para el texto con un idioma no predeterminado y el atributo "Lang" se adjunta a esta etiqueta.

Este valor se ignora cuando[`ExportDocumentStructure`](../exportdocumentstructure/) es`falso` .

### Ejemplos

Muestra cómo crear una etiqueta "Span" en la estructura del documento para exportar el idioma del texto.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");
builder.Writeln("Hola mundo!");

PdfSaveOptions saveOptions = new PdfSaveOptions
{
    // Tenga en cuenta que cuando "ExportDocumentStructure" es falso, "ExportLanguageToSpanTag" se ignora.
    ExportDocumentStructure = true, ExportLanguageToSpanTag = true
};

doc.Save(ArtifactsDir + "PdfSaveOptions.ExportLanguageToSpanTag.pdf", saveOptions);
```

### Ver también

* class [PdfSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../pdfsaveoptions/)
* asamblea [Aspose.Words](../../../)


