---
title: Enum ImagePixelFormat
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Saving.ImagePixelFormat перечисление. Указывает формат пикселей для сгенерированных изображений страниц документа.
type: docs
weight: 4960
url: /ru/net/aspose.words.saving/imagepixelformat/
---
## ImagePixelFormat enumeration

Указывает формат пикселей для сгенерированных изображений страниц документа.

```csharp
public enum ImagePixelFormat
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| Format16BppRgb555 | `0` | 16 бит на пиксель, RGB. |
| Format16BppRgb565 | `1` | 16 бит на пиксель, RGB. |
| Format16BppArgb1555 | `2` | 16 бит на пиксель, ARGB. |
| Format24BppRgb | `3` | 24 бита на пиксель, RGB. |
| Format32BppRgb | `4` | 32 бита на пиксель, RGB. |
| Format32BppArgb | `5` | 32 бита на пиксель, ARGB. |
| Format32BppPArgb | `6` | 32 бита на пиксель, ARGB, альфа-канал с предварительным умножением. |
| Format48BppRgb | `7` | 48 бит на пиксель, RGB. |
| Format64BppArgb | `8` | 64 бита на пиксель, ARGB. |
| Format64BppPArgb | `9` | 64 бита на пиксель, ARGB, альфа-канал с предварительным умножением. |
| Format1bppIndexed | `10` | 1 бит на пиксель, индексировано. |

### Примеры

Показывает, как выбрать скорость передачи битов на пиксель для преобразования документа в изображение.

```csharp
Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);

            builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
            builder.Writeln("Hello world!");
            builder.InsertImage(ImageDir + "Logo.jpg");

            Assert.That(20000, Is.LessThan(new FileInfo(ImageDir + "Logo.jpg").Length));

            // Когда мы сохраняем документ как изображение, мы можем передать объект SaveOptions в
            // выберите формат пикселей для изображения, которое будет сгенерировано операцией сохранения.
            // Различная скорость передачи битов на пиксель влияет на качество и размер файла сгенерированного изображения.
            ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png);
            imageSaveOptions.PixelFormat = imagePixelFormat;

            // Мы можем клонировать экземпляры ImageSaveOptions.
            Assert.AreNotEqual(imageSaveOptions, imageSaveOptions.Clone());

            doc.Save(ArtifactsDir + "ImageSaveOptions.PixelFormat.png", imageSaveOptions);

#if NET48 || JAVA
            switch (imagePixelFormat)
            {
                case ImagePixelFormat.Format1bppIndexed:
                    Assert.That(10000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.PixelFormat.png").Length));
                    break;
                case ImagePixelFormat.Format16BppRgb555:
                    Assert.That(80000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.PixelFormat.png").Length));
                    break;
                case ImagePixelFormat.Format24BppRgb:
                    Assert.That(125000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.PixelFormat.png").Length));
                    break;
                case ImagePixelFormat.Format32BppRgb:
                    Assert.That(150000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.PixelFormat.png").Length));
                    break;
                case ImagePixelFormat.Format48BppRgb:
                    Assert.That(200000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.PixelFormat.png").Length));
                    break;
            }
#elif NET5_0_OR_GREATER
            switch (imagePixelFormat)
            {
                case ImagePixelFormat.Format1bppIndexed:
                    Assert.That(10000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.PixelFormat.png").Length));
                    break;
                case ImagePixelFormat.Format24BppRgb:
                    Assert.That(70000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.PixelFormat.png").Length));
                    break;
                case ImagePixelFormat.Format16BppRgb555:
                case ImagePixelFormat.Format32BppRgb:
                case ImagePixelFormat.Format48BppRgb:
                    Assert.That(125000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.PixelFormat.png").Length));
                    break;
            }
#endif
```

### Смотрите также

* пространство имен [Aspose.Words.Saving](../../aspose.words.saving/)
* сборка [Aspose.Words](../../)


