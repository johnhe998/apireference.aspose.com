---
title: Class GraphicsQualityOptions
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Saving.GraphicsQualityOptions сорт. Позволяет указать доп.Graphics варианты качества.
type: docs
weight: 4780
url: /ru/net/aspose.words.saving/graphicsqualityoptions/
---
## GraphicsQualityOptions class

Позволяет указать доп.Graphics варианты качества.

```csharp
public class GraphicsQualityOptions
```

## Конструкторы

| Имя | Описание |
| --- | --- |
| [GraphicsQualityOptions](graphicsqualityoptions/)() | Конструктор по умолчанию. |

## Характеристики

| Имя | Описание |
| --- | --- |
| [CompositingMode](../../aspose.words.saving/graphicsqualityoptions/compositingmode/) { get; set; } | Получает или задает значение, указывающее, как составные изображения рисуются в этом объекте Graphics. |
| [CompositingQuality](../../aspose.words.saving/graphicsqualityoptions/compositingquality/) { get; set; } | Получает или задает качество рендеринга составных изображений, нарисованных на этом объекте Graphics. |
| [InterpolationMode](../../aspose.words.saving/graphicsqualityoptions/interpolationmode/) { get; set; } | Получает или задает режим интерполяции, связанный с этой графикой. |
| [SmoothingMode](../../aspose.words.saving/graphicsqualityoptions/smoothingmode/) { get; set; } | Получает или задает качество рендеринга для этой графики. |
| [StringFormat](../../aspose.words.saving/graphicsqualityoptions/stringformat/) { get; set; } | Получает или задает информацию о макете текста (например, выравнивание, ориентация и позиции табуляции), операции отображения (например, вставка многоточия и замена национальных цифр) и функции OpenType. |
| [TextRenderingHint](../../aspose.words.saving/graphicsqualityoptions/textrenderinghint/) { get; set; } | Получает или задает режим рендеринга для текста, связанного с этой графикой. |
| [UseTileFlipMode](../../aspose.words.saving/graphicsqualityoptions/usetileflipmode/) { get; set; } | Получает или устанавливает флаг, указывающий, является ли WrapMode TileFlipXY. |

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

* пространство имен [Aspose.Words.Saving](../../aspose.words.saving/)
* сборка [Aspose.Words](../../)


