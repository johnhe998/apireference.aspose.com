---
title: Class OutlineOptions
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Saving.OutlineOptions clase. Permite especificar opciones de contorno.
type: docs
weight: 5080
url: /es/net/aspose.words.saving/outlineoptions/
---
## OutlineOptions class

Permite especificar opciones de contorno.

```csharp
public class OutlineOptions
```

## Constructores

| Nombre | Descripción |
| --- | --- |
| [OutlineOptions](outlineoptions/)() | Constructor predeterminado |

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [BookmarksOutlineLevels](../../aspose.words.saving/outlineoptions/bookmarksoutlinelevels/) { get; } | Permite especificar el nivel de contorno de marcadores individuales. |
| [CreateMissingOutlineLevels](../../aspose.words.saving/outlineoptions/createmissingoutlinelevels/) { get; set; } | Obtiene o establece un valor que determina si se crean o no los niveles de esquema que faltan cuando el documento se exporta . |
| [CreateOutlinesForHeadingsInTables](../../aspose.words.saving/outlineoptions/createoutlinesforheadingsintables/) { get; set; } | Especifica si se crean o no esquemas para encabezados (párrafos formateados con los estilos de encabezado) dentro de las tablas. |
| [DefaultBookmarksOutlineLevel](../../aspose.words.saving/outlineoptions/defaultbookmarksoutlinelevel/) { get; set; } | Especifica el nivel predeterminado en el esquema del documento en el que se muestran los marcadores de Word. |
| [ExpandedOutlineLevels](../../aspose.words.saving/outlineoptions/expandedoutlinelevels/) { get; set; } | Especifica cuántos niveles en el esquema del documento se mostrarán expandidos cuando se visualice el archivo. |
| [HeadingsOutlineLevels](../../aspose.words.saving/outlineoptions/headingsoutlinelevels/) { get; set; } | Especifica cuántos niveles de encabezados (párrafos formateados con los estilos de encabezado) para incluir en el esquema del documento . |

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


