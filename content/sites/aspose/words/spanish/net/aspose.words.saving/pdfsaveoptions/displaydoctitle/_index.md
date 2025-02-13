---
title: PdfSaveOptions.DisplayDocTitle
second_title: Referencia de API de Aspose.Words para .NET
description: PdfSaveOptions propiedad. Un indicador que especifica si la barra de título de la ventana debe mostrar el título del documento tomado de la entrada Título del diccionario de información del documento.
type: docs
weight: 70
url: /es/net/aspose.words.saving/pdfsaveoptions/displaydoctitle/
---
## PdfSaveOptions.DisplayDocTitle property

Un indicador que especifica si la barra de título de la ventana debe mostrar el título del documento tomado de la entrada Título del diccionario de información del documento.

```csharp
public bool DisplayDocTitle { get; set; }
```

### Observaciones

Si`falso`, la barra de título debería mostrar el nombre del archivo PDF que contiene el documento.

Esta bandera es requerida por el cumplimiento de PDF/UA.`verdadero` El valor se usará automáticamente al guardar en PDF/UA.

El valor predeterminado es`falso`.

### Ejemplos

Muestra cómo mostrar el título del documento como barra de título.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

doc.BuiltInDocumentProperties.Title = "Windows bar pdf title";

// Crea un objeto "PdfSaveOptions" que podemos pasar al método "Guardar" del documento
// para modificar cómo ese método convierte el documento a .PDF.
// Establezca "DisplayDocTitle" en "true" para obtener algunos lectores de PDF, como Adobe Acrobat Pro,
// para mostrar el valor de la propiedad incorporada "Título" del documento en la pestaña que pertenece a este documento.
// Establezca "DisplayDocTitle" en "false" para que dichos lectores muestren el nombre de archivo del documento.
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions { DisplayDocTitle = displayDocTitle };

doc.Save(ArtifactsDir + "PdfSaveOptions.DocTitle.pdf", pdfSaveOptions);
```

### Ver también

* class [PdfSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../pdfsaveoptions/)
* asamblea [Aspose.Words](../../../)


