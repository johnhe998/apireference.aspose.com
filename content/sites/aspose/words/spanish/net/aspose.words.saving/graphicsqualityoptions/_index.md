---
title: Class GraphicsQualityOptions
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Saving.GraphicsQualityOptions clase. Permite especificar adicionalesGraphics opciones de calidad.
type: docs
weight: 4780
url: /es/net/aspose.words.saving/graphicsqualityoptions/
---
## GraphicsQualityOptions class

Permite especificar adicionalesGraphics opciones de calidad.

```csharp
public class GraphicsQualityOptions
```

## Constructores

| Nombre | Descripción |
| --- | --- |
| [GraphicsQualityOptions](graphicsqualityoptions/)() | Constructor predeterminado |

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [CompositingMode](../../aspose.words.saving/graphicsqualityoptions/compositingmode/) { get; set; } | Obtiene o establece un valor que especifica cómo se dibujan las imágenes compuestas en este Graphics. |
| [CompositingQuality](../../aspose.words.saving/graphicsqualityoptions/compositingquality/) { get; set; } | Obtiene o establece la calidad de representación de las imágenes compuestas dibujadas en este Graphics. |
| [InterpolationMode](../../aspose.words.saving/graphicsqualityoptions/interpolationmode/) { get; set; } | Obtiene o establece el modo de interpolación asociado con este Graphics. |
| [SmoothingMode](../../aspose.words.saving/graphicsqualityoptions/smoothingmode/) { get; set; } | Obtiene o establece la calidad de representación de este Graphics. |
| [StringFormat](../../aspose.words.saving/graphicsqualityoptions/stringformat/) { get; set; } | Obtiene o establece información de diseño de texto (como alineación, orientación y tabulaciones), manipulaciones de visualización (como inserción de puntos suspensivos y sustitución de dígitos nacionales) y funciones OpenType. |
| [TextRenderingHint](../../aspose.words.saving/graphicsqualityoptions/textrenderinghint/) { get; set; } | Obtiene o establece el modo de representación del texto asociado con este Graphics. |
| [UseTileFlipMode](../../aspose.words.saving/graphicsqualityoptions/usetileflipmode/) { get; set; } | Obtiene o establece un indicador que indica si WrapMode es TileFlipXY. |

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

* espacio de nombres [Aspose.Words.Saving](../../aspose.words.saving/)
* asamblea [Aspose.Words](../../)


