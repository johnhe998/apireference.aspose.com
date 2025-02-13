---
title: ImageWatermarkOptions.Scale
second_title: Справочник по API Aspose.Words для .NET
description: ImageWatermarkOptions свойство. Получает или задает коэффициент масштабирования выраженный в виде доли изображения. Значение по умолчанию 0  auto.
type: docs
weight: 30
url: /ru/net/aspose.words/imagewatermarkoptions/scale/
---
## ImageWatermarkOptions.Scale property

Получает или задает коэффициент масштабирования, выраженный в виде доли изображения. Значение по умолчанию 0 - auto.

```csharp
public double Scale { get; set; }
```

### Исключения

| исключение | условие |
| --- | --- |
| ArgumentOutOfRangeException | Выдает, когда аргумент находится вне диапазона допустимых значений. |

### Примечания

Допустимые значения находятся в диапазоне от 0 до 65,5 включительно.

Автоматическое масштабирование означает, что водяной знак будет масштабироваться до максимальной ширины и максимальной высоты относительно полей страницы.

### Примеры

Показывает, как создать водяной знак из изображения в локальной файловой системе.

```csharp
Document doc = new Document();

            // Изменяем внешний вид водяного знака изображения с помощью объекта ImageWatermarkOptions,
            // затем передать его при создании водяного знака из файла изображения.
            ImageWatermarkOptions imageWatermarkOptions = new ImageWatermarkOptions();
            imageWatermarkOptions.Scale = 5;
            imageWatermarkOptions.IsWashout = false;

#if NET48 || JAVA
            doc.Watermark.SetImage(Image.FromFile(ImageDir + "Logo.jpg"), imageWatermarkOptions);
#elif NET5_0_OR_GREATER || __MOBILE__
            using (SKBitmap image = SKBitmap.Decode(ImageDir + "Logo.jpg"))
            {
                doc.Watermark.SetImage(image, imageWatermarkOptions);
            }
#endif

            doc.Save(ArtifactsDir + "Document.ImageWatermark.docx");
```

### Смотрите также

* class [ImageWatermarkOptions](../)
* пространство имен [Aspose.Words](../../imagewatermarkoptions/)
* сборка [Aspose.Words](../../../)


