---
title: Enum PdfPageMode
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Saving.PdfPageMode enumeración. Especifica cómo se debe mostrar el documento PDF cuando se abre en el lector de PDF.
type: docs
weight: 5220
url: /es/net/aspose.words.saving/pdfpagemode/
---
## PdfPageMode enumeration

Especifica cómo se debe mostrar el documento PDF cuando se abre en el lector de PDF.

```csharp
public enum PdfPageMode
```

### Valores

| Nombre | Valor | Descripción |
| --- | --- | --- |
| UseNone | `0` | No se ven ni el contorno del documento ni las imágenes en miniatura. |
| UseOutlines | `1` | El contorno del documento está visible. Tenga en cuenta que si no hay contornos en el documento PDF, el panel de navegación de contornos no estará visible de todos modos. |
| UseThumbs | `2` | Las imágenes en miniatura son visibles. |
| FullScreen | `3` | Modo de pantalla completa, sin barra de menú, controles de ventana ni ninguna otra ventana visible. |
| UseOC | `4` | El panel de grupo de contenido opcional está visible. |
| UseAttachments | `5` | El panel de archivos adjuntos está visible. |

### Ejemplos

Muestra cómo configurar las instrucciones que deben seguir algunos lectores de PDF al abrir un documento de salida.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Crea un objeto "PdfSaveOptions" que podemos pasar al método "Guardar" del documento
// para modificar cómo ese método convierte el documento a .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Establezca la propiedad "PageMode" en "PdfPageMode.FullScreen" para que el lector de PDF abra el archivo guardado
// documento en modo de pantalla completa, que ocupa la pantalla del monitor y no tiene controles visibles.
// Establezca la propiedad "PageMode" en "PdfPageMode.UseThumbs" para que el lector de PDF muestre un panel separado
// con una miniatura para cada página del documento.
// Establezca la propiedad "PageMode" en "PdfPageMode.UseOC" para que el lector de PDF muestre un panel separado
// que nos permite trabajar con cualquier capa presente en el documento.
// Establezca la propiedad "PageMode" en "PdfPageMode.UseOutlines" para obtener el lector de PDF
// también para mostrar el contorno, si es posible.
// Establezca la propiedad "PageMode" en "PdfPageMode.UseNone" para que el lector de PDF muestre solo el documento en sí.
// Establezca la propiedad "PageMode" en "PdfPageMode.UseAttachments" para hacer visible el panel de archivos adjuntos.
options.PageMode = pageMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.PageMode.pdf", options);
```

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


