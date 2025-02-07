---
title: Class SaveOutputParameters
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Saving.SaveOutputParameters clase. Este objeto se devuelve a la persona que llama después de guardar un documento y contiene información adicional de que se ha generado o calculado durante la operación de guardado. La persona que llama puede usar o ignorar este objeto.
type: docs
weight: 5310
url: /es/net/aspose.words.saving/saveoutputparameters/
---
## SaveOutputParameters class

Este objeto se devuelve a la persona que llama después de guardar un documento y contiene información adicional de que se ha generado o calculado durante la operación de guardado. La persona que llama puede usar o ignorar este objeto.

```csharp
public class SaveOutputParameters
```

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [ContentType](../../aspose.words.saving/saveoutputparameters/contenttype/) { get; } | Devuelve la cadena de tipo de contenido (Tipo de medio de Internet) que identifica el tipo del documento guardado. |

### Ejemplos

Muestra cómo acceder a los parámetros de salida de la operación de guardado de un documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Después de guardar un documento, podemos acceder al tipo de medio de Internet (tipo MIME) del documento de salida recién creado.
SaveOutputParameters parameters = doc.Save(ArtifactsDir + "Document.SaveOutputParameters.doc");

Assert.AreEqual("application/msword", parameters.ContentType);

// Esta propiedad cambia según el formato de guardado.
parameters = doc.Save(ArtifactsDir + "Document.SaveOutputParameters.pdf");

Assert.AreEqual("application/pdf", parameters.ContentType);
```

### Ver también

* espacio de nombres [Aspose.Words.Saving](../../aspose.words.saving/)
* asamblea [Aspose.Words](../../)


