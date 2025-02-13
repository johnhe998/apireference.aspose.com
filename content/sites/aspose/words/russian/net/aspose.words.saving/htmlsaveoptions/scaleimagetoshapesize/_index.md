---
title: HtmlSaveOptions.ScaleImageToShapeSize
second_title: Справочник по API Aspose.Words для .NET
description: HtmlSaveOptions свойство. Указывает масштабируются ли изображения с помощью Aspose.Words до размера ограничивающей фигуры при экспорте в HTML MHTML или EPUB. Значение по умолчаниюистинный .
type: docs
weight: 450
url: /ru/net/aspose.words.saving/htmlsaveoptions/scaleimagetoshapesize/
---
## HtmlSaveOptions.ScaleImageToShapeSize property

Указывает, масштабируются ли изображения с помощью Aspose.Words до размера ограничивающей фигуры при экспорте в HTML, MHTML или EPUB. Значение по умолчанию:`истинный` .

```csharp
public bool ScaleImageToShapeSize { get; set; }
```

### Примечания

Изображение в документе Microsoft Word представляет собой фигуру. Форма имеет размер, а image имеет свой собственный размер. Размеры напрямую не связаны. Например, изображение может иметь размер 1024x786 пикселей, , но форма, отображающая это изображение, может иметь размер 400x300 точек.

Чтобы изображение отображалось в браузере, оно должно быть масштабировано до размера формы. `ScaleImageToShapeSize` Свойство определяет, где происходит масштабирование изображения : в Aspose.Words при экспорте в HTML или в браузере при отображении документа.

Когда`ScaleImageToShapeSize` является`истинный` , изображение масштабируется Aspose.Words с использованием масштабирования высокого качества при экспорте в HTML. Когда`ScaleImageToShapeSize` это`ЛОЖЬ`изображение выводится в исходном размере, и браузер должен масштабировать его.

Как правило, браузеры делают быстрое и некачественное масштабирование. В результате вы обычно получаете лучшее качество отображения в браузере и меньший размер файла при`ScaleImageToShapeSize` является`истинный` , , но лучшее качество печати и более быстрое преобразование при`ScaleImageToShapeSize` является`ЛОЖЬ`.

### Примеры

Показывает, как отключить масштабирование изображений до размеров их родительской формы при сохранении в формате .html.

```csharp
Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);

            // Вставьте фигуру, содержащую изображение, а затем сделайте эту фигуру значительно меньше изображения.
#if NET48 || JAVA
            Image image = Image.FromFile(ImageDir + "Transparent background logo.png");

            Assert.AreEqual(400, image.Size.Width);
            Assert.AreEqual(400, image.Size.Height);
#elif NET5_0_OR_GREATER
            SKBitmap image = SKBitmap.Decode(ImageDir + "Transparent background logo.png");

            Assert.AreEqual(400, image.Width);
            Assert.AreEqual(400, image.Height);
#endif

            Shape imageShape = builder.InsertImage(image);
            imageShape.Width = 50;
            imageShape.Height = 50;

            // Сохранение документа, содержащего фигуры с изображениями, в HTML создаст файл изображения в локальной файловой системе
            // для каждой такой формы. Выходной HTML-документ будет использовать <image> теги для ссылки и отображения этих изображений.
            // Когда мы сохраняем документ в HTML, мы можем передать объект SaveOptions, чтобы определить
            // следует ли масштабировать все изображения внутри фигур до размеров их фигур.
            // Установка флага "ScaleImageToShapeSize" в "true" уменьшит каждое изображение
            // к размеру фигуры, которая его содержит, так что никакие сохраненные изображения не будут больше, чем требуется документу.
            // Установка флага "ScaleImageToShapeSize" в "false" сохранит исходные размеры этих изображений,
            // что займет больше места в обмен на сохранение качества изображения.
            HtmlSaveOptions options = new HtmlSaveOptions { ScaleImageToShapeSize = scaleImageToShapeSize };

            doc.Save(ArtifactsDir + "HtmlSaveOptions.ScaleImageToShapeSize.html", options);

            FileInfo fileInfo = new FileInfo(ArtifactsDir + "HtmlSaveOptions.ScaleImageToShapeSize.001.png");

#if NET48 || JAVA
        if (scaleImageToShapeSize)
            Assert.That(3000, Is.AtLeast(fileInfo.Length));
        else
            Assert.That(20000, Is.LessThan(fileInfo.Length));
#elif NET5_0_OR_GREATER
        if (scaleImageToShapeSize)
            Assert.That(10000, Is.AtLeast(fileInfo.Length));
        else
            Assert.That(30000, Is.LessThan(fileInfo.Length));
#endif
```

### Смотрите также

* property [ImageResolution](../imageresolution/)
* class [HtmlSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../htmlsaveoptions/)
* сборка [Aspose.Words](../../../)


