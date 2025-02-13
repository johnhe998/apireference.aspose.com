---
title: ImageSaveOptions.TiffBinarizationMethod
second_title: Справочник по API Aspose.Words для .NET
description: ImageSaveOptions свойство. Получает или задает метод используемый при преобразовании изображений в формат 1 бит/пиксель  когдаSaveFormat это SaveFormat.Tiff и TiffCompression равно TiffCompression.Ccitt3 или TiffCompression.Ccitt4.
type: docs
weight: 160
url: /ru/net/aspose.words.saving/imagesaveoptions/tiffbinarizationmethod/
---
## ImageSaveOptions.TiffBinarizationMethod property

Получает или задает метод, используемый при преобразовании изображений в формат 1 бит/пиксель , когда[`SaveFormat`](../saveformat/) это SaveFormat.Tiff и [`TiffCompression`](../tiffcompression/) равно TiffCompression.Ccitt3 или TiffCompression.Ccitt4.

```csharp
public ImageBinarizationMethod TiffBinarizationMethod { get; set; }
```

### Примечания

Значение по умолчанию — ImageBinarizationMethod.Threshold.

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

* enum [ImageBinarizationMethod](../../imagebinarizationmethod/)
* class [ImageSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../imagesaveoptions/)
* сборка [Aspose.Words](../../../)


