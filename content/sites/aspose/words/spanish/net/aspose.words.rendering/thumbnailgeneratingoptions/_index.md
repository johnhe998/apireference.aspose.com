---
title: Class ThumbnailGeneratingOptions
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Rendering.ThumbnailGeneratingOptions clase. Se puede usar para especificar opciones adicionales al generar una miniatura para un documento.
type: docs
weight: 4340
url: /es/net/aspose.words.rendering/thumbnailgeneratingoptions/
---
## ThumbnailGeneratingOptions class

Se puede usar para especificar opciones adicionales al generar una miniatura para un documento.

```csharp
public class ThumbnailGeneratingOptions
```

## Constructores

| Nombre | Descripción |
| --- | --- |
| [ThumbnailGeneratingOptions](thumbnailgeneratingoptions/)() | Constructor predeterminado |

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [GenerateFromFirstPage](../../aspose.words.rendering/thumbnailgeneratingoptions/generatefromfirstpage/) { get; set; } | Especifica si generar una miniatura desde la primera página del documento o desde la primera imagen. |
| [ThumbnailSize](../../aspose.words.rendering/thumbnailgeneratingoptions/thumbnailsize/) { get; set; } | Tamaño de la miniatura generada en píxeles. El valor predeterminado es 600x900. |

### Observaciones

El usuario puede llamar al método[`UpdateThumbnail`](../../aspose.words/document/updatethumbnail/) para generar [`Thumbnail`](../../aspose.words.properties/builtindocumentproperties/thumbnail/) para un documento.

### Ejemplos

Muestra cómo actualizar la miniatura de un documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");
builder.InsertImage(ImageDir + "Logo.jpg");

// Hay dos formas de configurar una imagen en miniatura al guardar un documento en .epub.
// 1 - Usa la primera página del documento:
doc.UpdateThumbnail();
doc.Save(ArtifactsDir + "Document.UpdateThumbnail.FirstPage.epub");

// 2 - Usa la primera imagen encontrada en el documento:
ThumbnailGeneratingOptions options = new ThumbnailGeneratingOptions();
options.ThumbnailSize = new Size(400, 400);
options.GenerateFromFirstPage = false;

doc.UpdateThumbnail(options);
doc.Save(ArtifactsDir + "Document.UpdateThumbnail.FirstImage.epub");
```

### Ver también

* espacio de nombres [Aspose.Words.Rendering](../../aspose.words.rendering/)
* asamblea [Aspose.Words](../../)


