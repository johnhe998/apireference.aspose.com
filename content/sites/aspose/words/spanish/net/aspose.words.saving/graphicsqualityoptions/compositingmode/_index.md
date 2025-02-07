---
title: GraphicsQualityOptions.CompositingMode
second_title: Referencia de API de Aspose.Words para .NET
description: GraphicsQualityOptions propiedad. Obtiene o establece un valor que especifica cómo se dibujan las imágenes compuestas en este Graphics.
type: docs
weight: 20
url: /es/net/aspose.words.saving/graphicsqualityoptions/compositingmode/
---
## GraphicsQualityOptions.CompositingMode property

Obtiene o establece un valor que especifica cómo se dibujan las imágenes compuestas en este Graphics.

```csharp
public CompositingMode? CompositingMode { get; set; }
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


