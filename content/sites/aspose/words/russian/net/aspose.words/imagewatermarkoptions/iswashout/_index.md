---
title: ImageWatermarkOptions.IsWashout
second_title: Справочник по API Aspose.Words для .NET
description: ImageWatermarkOptions свойство. Получает или задает логическое значение отвечающее за размытие водяного знака. Значение по умолчанию  True.
type: docs
weight: 20
url: /ru/net/aspose.words/imagewatermarkoptions/iswashout/
---
## ImageWatermarkOptions.IsWashout property

Получает или задает логическое значение, отвечающее за размытие водяного знака. Значение по умолчанию — True.

```csharp
public bool IsWashout { get; set; }
```

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


