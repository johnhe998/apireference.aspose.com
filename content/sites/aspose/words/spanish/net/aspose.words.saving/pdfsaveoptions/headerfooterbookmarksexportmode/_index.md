---
title: PdfSaveOptions.HeaderFooterBookmarksExportMode
second_title: Referencia de API de Aspose.Words para .NET
description: PdfSaveOptions propiedad. Determina cómo se exportan los marcadores en encabezados/pies de página.
type: docs
weight: 150
url: /es/net/aspose.words.saving/pdfsaveoptions/headerfooterbookmarksexportmode/
---
## PdfSaveOptions.HeaderFooterBookmarksExportMode property

Determina cómo se exportan los marcadores en encabezados/pies de página.

```csharp
public HeaderFooterBookmarksExportMode HeaderFooterBookmarksExportMode { get; set; }
```

### Observaciones

El valor predeterminado esAll.

Esta propiedad se utiliza junto con la[`OutlineOptions`](../outlineoptions/) opción.

### Ejemplos

Programas para procesar marcadores en encabezados/pies de página en un documento que estamos renderizando a PDF.

```csharp
Document doc = new Document(MyDir + "Bookmarks in headers and footers.docx");

// Crea un objeto "PdfSaveOptions" que podemos pasar al método "Guardar" del documento
// para modificar cómo ese método convierte el documento a .PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Establezca la propiedad "PageMode" en "PdfPageMode.UseOutlines" para mostrar el panel de navegación del esquema en el PDF de salida.
saveOptions.PageMode = PdfPageMode.UseOutlines;

// Establecer la propiedad "DefaultBookmarksOutlineLevel" en "1" para mostrar todo
// marcadores en el primer nivel del esquema en el PDF de salida.
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;

// Establecer la propiedad "HeaderFooterBookmarksExportMode" en "HeaderFooterBookmarksExportMode.None" para
// no exportar ningún marcador que esté dentro de los encabezados/pies de página.
// Establecer la propiedad "HeaderFooterBookmarksExportMode" en "HeaderFooterBookmarksExportMode.First" para
// exportar solo marcadores en el encabezado/pie de página de la primera sección.
// Establecer la propiedad "HeaderFooterBookmarksExportMode" en "HeaderFooterBookmarksExportMode.All" para
// exportar marcadores que están en todos los encabezados/pies de página.
saveOptions.HeaderFooterBookmarksExportMode = headerFooterBookmarksExportMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.HeaderFooterBookmarksExportMode.pdf", saveOptions);
```

### Ver también

* enum [HeaderFooterBookmarksExportMode](../../headerfooterbookmarksexportmode/)
* class [PdfSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../pdfsaveoptions/)
* asamblea [Aspose.Words](../../../)


