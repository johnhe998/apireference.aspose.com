---
title: ImageSaveOptions.ImageContrast
second_title: Справочник по API Aspose.Words для .NET
description: ImageSaveOptions свойство. Получает или задает контраст для сгенерированных изображений.
type: docs
weight: 60
url: /ru/net/aspose.words.saving/imagesaveoptions/imagecontrast/
---
## ImageSaveOptions.ImageContrast property

Получает или задает контраст для сгенерированных изображений.

```csharp
public float ImageContrast { get; set; }
```

### Примечания

Это свойство действует только при сохранении в форматы растровых изображений.

Значение по умолчанию — 0,5. Значение должно быть в диапазоне от 0 до 1.

### Примеры

Показывает, как редактировать изображение, пока Aspose.Words преобразует документ в один.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
builder.Writeln("Hello world!");
builder.InsertImage(ImageDir + "Logo.jpg");

// Когда мы сохраняем документ как изображение, мы можем передать объект SaveOptions в
// редактируем изображение во время его рендеринга операцией сохранения.
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Png)
{
    // Мы можем настроить эти свойства, чтобы изменить яркость и контрастность изображения.
    // Оба имеют шкалу от 0 до 1 и по умолчанию имеют значение 0,5.
    ImageBrightness = 0.3f,
    ImageContrast = 0.7f,

    // С помощью этих свойств мы можем настроить горизонтальное и вертикальное разрешение.
    // Это повлияет на размеры изображения.
    // Значение по умолчанию для этих свойств — 96,0 для разрешения 96 точек на дюйм.
    HorizontalResolution = 72f,
    VerticalResolution = 72f,

    // Мы можем масштабировать изображение, используя это свойство. Значение по умолчанию — 1,0 для масштабирования 100 %.
    // Мы можем использовать это свойство, чтобы отменить любые изменения размеров изображения, которые могут быть вызваны изменением разрешения.
    Scale = 96f / 72f
};

doc.Save(ArtifactsDir + "ImageSaveOptions.EditImage.png", options);
```

### Смотрите также

* class [ImageSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../imagesaveoptions/)
* сборка [Aspose.Words](../../../)


