---
title: GraphicsQualityOptions.CompositingMode
second_title: Справочник по API Aspose.Words для .NET
description: GraphicsQualityOptions свойство. Получает или задает значение указывающее как составные изображения рисуются в этом объекте Graphics.
type: docs
weight: 20
url: /ru/net/aspose.words.saving/graphicsqualityoptions/compositingmode/
---
## GraphicsQualityOptions.CompositingMode property

Получает или задает значение, указывающее, как составные изображения рисуются в этом объекте Graphics.

```csharp
public CompositingMode? CompositingMode { get; set; }
```

### Примеры

Показывает, как установить параметры качества рендеринга при преобразовании документов в форматы изображений.

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

### Смотрите также

* class [GraphicsQualityOptions](../)
* пространство имен [Aspose.Words.Saving](../../graphicsqualityoptions/)
* сборка [Aspose.Words](../../../)


