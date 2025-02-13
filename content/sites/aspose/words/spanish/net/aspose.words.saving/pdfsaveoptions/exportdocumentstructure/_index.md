---
title: PdfSaveOptions.ExportDocumentStructure
second_title: Referencia de API de Aspose.Words para .NET
description: PdfSaveOptions propiedad. Obtiene o establece un valor que determina si se exporta o no la estructura del documento.
type: docs
weight: 120
url: /es/net/aspose.words.saving/pdfsaveoptions/exportdocumentstructure/
---
## PdfSaveOptions.ExportDocumentStructure property

Obtiene o establece un valor que determina si se exporta o no la estructura del documento.

```csharp
public bool ExportDocumentStructure { get; set; }
```

### Observaciones

Este valor se ignora cuando se guarda en PDF/A-1a, PDF/A-2a y PDF/UA-1 porque se requiere la estructura del documento para este cumplimiento.

Tenga en cuenta que exportar la estructura del documento aumenta significativamente el consumo de memoria, especialmente para los documentos grandes.

### Ejemplos

Muestra cómo conservar los elementos de la estructura del documento, lo que puede ayudar a interpretar nuestro documento mediante programación.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
builder.Writeln("Hello world!");
builder.ParagraphFormat.Style = doc.Styles["Normal"];
builder.Write(
    "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

// Crea un objeto "PdfSaveOptions" que podemos pasar al método "Guardar" del documento
// para modificar cómo ese método convierte el documento a .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Establezca la propiedad "ExportDocumentStructure" en "true" para que la estructura del documento, tales etiquetas, estén disponibles a través del
// Panel de navegación "Contenido" de Adobe Acrobat a costa de aumentar el tamaño del archivo.
// Establezca la propiedad "ExportDocumentStructure" en "false" para no exportar la estructura del documento.
options.ExportDocumentStructure = exportDocumentStructure;

// Supongamos que exportamos la estructura del documento mientras guardamos este documento. En ese caso,
// podemos abrirlo usando Adobe Acrobat y encontrar etiquetas para elementos como el encabezado
// y el siguiente párrafo a través de "Ver" -> "Mostrar/Ocultar" -> "Paneles de navegación" -> "Etiquetas".
doc.Save(ArtifactsDir + "PdfSaveOptions.ExportDocumentStructure.pdf", options);
```

### Ver también

* class [PdfSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../pdfsaveoptions/)
* asamblea [Aspose.Words](../../../)


