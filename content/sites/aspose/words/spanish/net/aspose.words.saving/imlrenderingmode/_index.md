---
title: Enum ImlRenderingMode
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Saving.ImlRenderingMode enumeración. Especifica cómo se representan los objetos de tinta InkML en formatos de página fijos.
type: docs
weight: 4990
url: /es/net/aspose.words.saving/imlrenderingmode/
---
## ImlRenderingMode enumeration

Especifica cómo se representan los objetos de tinta (InkML) en formatos de página fijos.

```csharp
public enum ImlRenderingMode
```

### Valores

| Nombre | Valor | Descripción |
| --- | --- | --- |
| Fallback | `0` | Si la forma alternativa está disponible para el objeto de tinta (InkML), Aspose.Words representa la forma alternativa en lugar de InkML. |
| InkML | `1` | Aspose.Words ignora la forma alternativa del objeto de tinta (InkML) y representa InkML en sí mismo. Este es el modo predeterminado. |

### Ejemplos

Muestra cómo renderizar un objeto Ink.

```csharp
Document doc = new Document(MyDir + "Ink object.docx");

// Establecer 'ImlRenderingMode.InkML' ignora la forma alternativa del objeto de tinta (InkML) y representa InkML en sí.
// Si el resultado de la renderización no es satisfactorio,
// utilice 'ImlRenderingMode.Fallback' para obtener un resultado similar a las versiones anteriores.
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Jpeg)
{
    ImlRenderingMode = ImlRenderingMode.InkML
};

doc.Save(ArtifactsDir + "ImageSaveOptions.RenderInkObject.jpeg", saveOptions);
```

### Ver también

* espacio de nombres [Aspose.Words.Saving](../../aspose.words.saving/)
* asamblea [Aspose.Words](../../)


