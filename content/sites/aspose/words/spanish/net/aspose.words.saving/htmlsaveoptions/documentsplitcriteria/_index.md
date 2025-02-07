---
title: HtmlSaveOptions.DocumentSplitCriteria
second_title: Referencia de API de Aspose.Words para .NET
description: HtmlSaveOptions propiedad. Especifica cómo se debe dividir el documento al guardar enHtml oEpub formato. El valor predeterminado esNone para HTML y HeadingParagraph para EPUB.
type: docs
weight: 80
url: /es/net/aspose.words.saving/htmlsaveoptions/documentsplitcriteria/
---
## HtmlSaveOptions.DocumentSplitCriteria property

Especifica cómo se debe dividir el documento al guardar enHtml oEpub formato. El valor predeterminado esNone para HTML y HeadingParagraph para EPUB.

```csharp
public DocumentSplitCriteria DocumentSplitCriteria { get; set; }
```

### Observaciones

Normalmente, desearía guardar un documento en HTML como un solo archivo. Pero en algunos casos es preferible dividir la salida en varias páginas HTML más pequeñas. Al guardar en formato HTML, estas páginas se enviarán a archivos o secuencias individuales. Al guardar en formato EPUB se incorporarán a los paquetes correspondientes.

Un documento no se puede dividir cuando se guarda en formato MHTML.

### Ejemplos

Muestra cómo usar una codificación específica al guardar un documento en .epub.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Use un objeto SaveOptions para especificar la codificación de un documento que guardaremos.
HtmlSaveOptions saveOptions = new HtmlSaveOptions();
saveOptions.SaveFormat = SaveFormat.Epub;
saveOptions.Encoding = Encoding.UTF8;

// Por defecto, un documento de salida .epub tendrá todo su contenido en una parte HTML.
// Un criterio de división nos permite segmentar el documento en varias partes HTML.
// Estableceremos los criterios para dividir el documento en párrafos de encabezado.
// Esto es útil para lectores que no pueden leer archivos HTML más grandes que un tamaño específico.
saveOptions.DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph;

// Especificar que queremos exportar las propiedades del documento.
saveOptions.ExportDocumentProperties = true;

doc.Save(ArtifactsDir + "HtmlSaveOptions.Doc2EpubSaveOptions.epub", saveOptions);
```

### Ver también

* enum [DocumentSplitCriteria](../../documentsplitcriteria/)
* class [HtmlSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../htmlsaveoptions/)
* asamblea [Aspose.Words](../../../)


