---
title: GraphicsQualityOptions.StringFormat
second_title: Referencia de API de Aspose.Words para .NET
description: GraphicsQualityOptions propiedad. Obtiene o establece información de diseño de texto como alineación orientación y tabulaciones manipulaciones de visualización como inserción de puntos suspensivos y sustitución de dígitos nacionales y funciones OpenType.
type: docs
weight: 60
url: /es/net/aspose.words.saving/graphicsqualityoptions/stringformat/
---
## GraphicsQualityOptions.StringFormat property

Obtiene o establece información de diseño de texto (como alineación, orientación y tabulaciones), manipulaciones de visualización (como inserción de puntos suspensivos y sustitución de dígitos nacionales) y funciones OpenType.

```csharp
public StringFormat StringFormat { get; set; }
```

### Ejemplos

Muestra cómo configurar las opciones de calidad de procesamiento al convertir documentos a formatos de imagen.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

GraphicsQualityOptions qualityOptions = new GraphicsQualityOptions
{
    SmoothingMode = SmoothingMode.AntiAlias,
    TextRenderingHint = TextRenderingHint.ClearTypeGridFit,
    CompositingMode = CompositingMode.SourceOver,
    CompositingQuality = CompositingQuality.HighQuality,
    InterpolationMode = InterpolationMode.High,
    StringFormat = StringFormat.GenericTypographic
};

ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Jpeg);
saveOptions.GraphicsQualityOptions = qualityOptions;

doc.Save(ArtifactsDir + "ImageSaveOptions.GraphicsQuality.jpg", saveOptions);
```

### Ver también

* class [GraphicsQualityOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../graphicsqualityoptions/)
* asamblea [Aspose.Words](../../../)


