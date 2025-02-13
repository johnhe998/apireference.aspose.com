---
title: ImageSaveOptions.GraphicsQualityOptions
second_title: Referencia de API de Aspose.Words para .NET
description: ImageSaveOptions propiedad. Permite especificar el modo de renderizado y la calidad para elGraphics objeto.
type: docs
weight: 20
url: /es/net/aspose.words.saving/imagesaveoptions/graphicsqualityoptions/
---
## ImageSaveOptions.GraphicsQualityOptions property

Permite especificar el modo de renderizado y la calidad para elGraphics objeto.

```csharp
public GraphicsQualityOptions GraphicsQualityOptions { get; set; }
```

### Observaciones

Utilice esta propiedad para anular la configuración de gráficos proporcionada por el motor Aspose.Words de forma predeterminada.

Solo surtirá efecto cuando un documento se guarde en un formato similar a una imagen.

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

* class [GraphicsQualityOptions](../../graphicsqualityoptions/)
* class [ImageSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../imagesaveoptions/)
* asamblea [Aspose.Words](../../../)


