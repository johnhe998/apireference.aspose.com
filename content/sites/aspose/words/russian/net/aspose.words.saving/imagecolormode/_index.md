---
title: Enum ImageColorMode
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Saving.ImageColorMode перечисление. Задает цветовой режим для сгенерированных изображений страниц документа.
type: docs
weight: 4950
url: /ru/net/aspose.words.saving/imagecolormode/
---
## ImageColorMode enumeration

Задает цветовой режим для сгенерированных изображений страниц документа.

```csharp
public enum ImageColorMode
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| None | `0` | Страницы документа будут отображаться как цветные изображения. |
| Grayscale | `1` | Страницы документа будут отображаться как изображения в градациях серого. |
| BlackAndWhite | `2` | Страницы документа будут отображаться как черно-белые изображения. |

### Примеры

Показывает, как установить цветовой режим при отображении документов.

```csharp
Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);

            builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
            builder.Writeln("Hello world!");
            builder.InsertImage(ImageDir + "Logo.jpg");

            Assert.That(20000, Is.LessThan(new FileInfo(ImageDir + "Logo.jpg").Length));

            // Когда мы сохраняем документ как изображение, мы можем передать объект SaveOptions в
            // выбор цветового режима для изображения, которое будет сгенерировано операцией сохранения.
            // Если мы установим для свойства "ImageColorMode" значение "ImageColorMode.BlackAndWhite",
            // операция сохранения применит уменьшение цвета в градациях серого при рендеринге документа.
             // Если мы установим для свойства "ImageColorMode" значение "ImageColorMode.Grayscale",
            // операция сохранения преобразует документ в монохромное изображение.
            // Если мы установим для свойства "ImageColorMode" значение "Нет", операция сохранения применит метод по умолчанию
            // и сохранить все цвета документа в выходном изображении.
            ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png);
            imageSaveOptions.ImageColorMode = imageColorMode;

            doc.Save(ArtifactsDir + "ImageSaveOptions.ColorMode.png", imageSaveOptions);

#if NET48 || JAVA
            switch (imageColorMode)
            {
                case ImageColorMode.None:
                    Assert.That(150000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.ColorMode.png").Length));
                    break;
                case ImageColorMode.Grayscale:
                    Assert.That(80000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.ColorMode.png").Length));
                    break;
                case ImageColorMode.BlackAndWhite:
                    Assert.That(20000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.ColorMode.png").Length));
                    break;
            }
#elif NET5_0_OR_GREATER
            switch (imageColorMode)
            {
                case ImageColorMode.None:
                    Assert.That(120000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.ColorMode.png").Length));
                    break;
                case ImageColorMode.Grayscale:
                    Assert.That(80000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.ColorMode.png").Length));
                    break;
                case ImageColorMode.BlackAndWhite:
                    Assert.That(20000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.ColorMode.png").Length));
                    break;
            }
#endif
```

### Смотрите также

* пространство имен [Aspose.Words.Saving](../../aspose.words.saving/)
* сборка [Aspose.Words](../../)


