---
title: Enum HeaderFooterBookmarksExportMode
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Saving.HeaderFooterBookmarksExportMode enumeración. Especifica cómo se exportan los marcadores en encabezados/pies de página.
type: docs
weight: 4790
url: /es/net/aspose.words.saving/headerfooterbookmarksexportmode/
---
## HeaderFooterBookmarksExportMode enumeration

Especifica cómo se exportan los marcadores en encabezados/pies de página.

```csharp
public enum HeaderFooterBookmarksExportMode
```

### Valores

| Nombre | Valor | Descripción |
| --- | --- | --- |
| None | `0` | Los marcadores en encabezados/pies de página no se exportan. |
| First | `1` | Solo se exporta el marcador del primer encabezado/pie de página de la sección. |
| All | `2` | Se exportan los marcadores en todos los encabezados/pies de página. |

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

* espacio de nombres [Aspose.Words.Saving](../../aspose.words.saving/)
* asamblea [Aspose.Words](../../)


