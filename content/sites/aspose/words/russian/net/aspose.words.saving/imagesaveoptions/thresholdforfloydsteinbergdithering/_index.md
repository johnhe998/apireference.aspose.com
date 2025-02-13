---
title: ImageSaveOptions.ThresholdForFloydSteinbergDithering
second_title: Справочник по API Aspose.Words для .NET
description: ImageSaveOptions свойство. Получает или задает пороговое значение определяющее значение ошибки бинаризации в методе ФлойдаСтейнберга. приImageBinarizationMethod это ImageBinarizationMethod.FloydSteinbergDithering.
type: docs
weight: 150
url: /ru/net/aspose.words.saving/imagesaveoptions/thresholdforfloydsteinbergdithering/
---
## ImageSaveOptions.ThresholdForFloydSteinbergDithering property

Получает или задает пороговое значение, определяющее значение ошибки бинаризации в методе Флойда-Стейнберга. при[`ImageBinarizationMethod`](../../imagebinarizationmethod/) это ImageBinarizationMethod.FloydSteinbergDithering.

```csharp
public byte ThresholdForFloydSteinbergDithering { get; set; }
```

### Примечания

Значение по умолчанию — 128.

### Примеры

Показывает, как установить порог ошибки бинаризации TIFF при использовании метода Флойда-Стейнберга для визуализации изображения TIFF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
builder.Writeln("Hello world!");
builder.InsertImage(ImageDir + "Logo.jpg");

// Когда мы сохраняем документ в формате TIFF, мы можем передать объект SaveOptions в
// настроить сглаживание, которое Aspose.Words будет применять при рендеринге этого изображения.
// Значение свойства ThresholdForFloydSteinbergDithering по умолчанию равно 128.
// Чем выше значение, тем темнее изображение.
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Tiff)
{
    TiffCompression = TiffCompression.Ccitt3,
    TiffBinarizationMethod = ImageBinarizationMethod.FloydSteinbergDithering,
    ThresholdForFloydSteinbergDithering = 240
};

doc.Save(ArtifactsDir + "ImageSaveOptions.FloydSteinbergDithering.tiff", options);
```

### Смотрите также

* class [ImageSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../imagesaveoptions/)
* сборка [Aspose.Words](../../../)


