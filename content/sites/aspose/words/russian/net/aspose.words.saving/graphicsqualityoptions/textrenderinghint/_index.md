---
title: GraphicsQualityOptions.TextRenderingHint
second_title: Справочник по API Aspose.Words для .NET
description: GraphicsQualityOptions свойство. Получает или задает режим рендеринга для текста связанного с этой графикой.
type: docs
weight: 70
url: /ru/net/aspose.words.saving/graphicsqualityoptions/textrenderinghint/
---
## GraphicsQualityOptions.TextRenderingHint property

Получает или задает режим рендеринга для текста, связанного с этой графикой.

```csharp
public TextRenderingHint? TextRenderingHint { get; set; }
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


