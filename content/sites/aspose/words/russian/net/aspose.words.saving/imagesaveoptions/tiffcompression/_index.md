---
title: ImageSaveOptions.TiffCompression
second_title: Справочник по API Aspose.Words для .NET
description: ImageSaveOptions свойство. Получает или задает тип сжатия применяемый при сохранении сгенерированных изображений в формате TIFF.
type: docs
weight: 170
url: /ru/net/aspose.words.saving/imagesaveoptions/tiffcompression/
---
## ImageSaveOptions.TiffCompression property

Получает или задает тип сжатия, применяемый при сохранении сгенерированных изображений в формате TIFF.

```csharp
public TiffCompression TiffCompression { get; set; }
```

### Примечания

Действует только при сохранении в TIFF.

Значение по умолчаниюLzw.

### Примеры

Показывает, как выбрать схему сжатия для применения к документу, который мы конвертируем в изображение TIFF.

```csharp
Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);

            builder.InsertImage(ImageDir + "Logo.jpg");

            // Создаем объект "ImageSaveOptions", который мы можем передать в метод "Сохранить" документа
            // чтобы изменить способ, которым этот метод преобразует документ в изображение.
            ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Tiff);

            // Установите для свойства "TiffCompression" значение "TiffCompression.None", чтобы не применять сжатие при сохранении,
            // что может привести к очень большому выходному файлу.
            // Установите для свойства "TiffCompression" значение "TiffCompression.Rle", чтобы применить сжатие RLE
            // Установите для свойства "TiffCompression" значение "TiffCompression.Lzw", чтобы применить сжатие LZW.
            // Установите для свойства "TiffCompression" значение "TiffCompression.Ccitt3", чтобы применить сжатие CCITT3.
            // Установите для свойства "TiffCompression" значение "TiffCompression.Ccitt4", чтобы применить сжатие CCITT4.
            options.TiffCompression = tiffCompression;

            doc.Save(ArtifactsDir + "ImageSaveOptions.TiffImageCompression.tiff", options);

            switch (tiffCompression)
            {
                case TiffCompression.None:
                    Assert.That(3000000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.TiffImageCompression.tiff").Length));
                    break;
                case TiffCompression.Rle:
#if NET5_0_OR_GREATER
                    Assert.That(6000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.TiffImageCompression.tiff").Length));
#else
                    Assert.That(600000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.TiffImageCompression.tiff").Length));
#endif
                    break;
                case TiffCompression.Lzw:
                    Assert.That(200000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.TiffImageCompression.tiff").Length));
                    break;
                case TiffCompression.Ccitt3:
                    Assert.That(90000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.TiffImageCompression.tiff").Length));
                    break;
                case TiffCompression.Ccitt4:
                    Assert.That(20000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.TiffImageCompression.tiff").Length));
                    break;
            }
```

### Смотрите также

* enum [TiffCompression](../../tiffcompression/)
* class [ImageSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../imagesaveoptions/)
* сборка [Aspose.Words](../../../)


