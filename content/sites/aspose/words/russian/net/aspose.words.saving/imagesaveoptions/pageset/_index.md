---
title: ImageSaveOptions.PageSet
second_title: Справочник по API Aspose.Words для .NET
description: ImageSaveOptions свойство. Получает или задает отображаемые страницы. По умолчанию  все страницы документа.
type: docs
weight: 90
url: /ru/net/aspose.words.saving/imagesaveoptions/pageset/
---
## ImageSaveOptions.PageSet property

Получает или задает отображаемые страницы. По умолчанию — все страницы документа.

```csharp
public PageSet PageSet { get; set; }
```

### Примечания

Это свойство действует только при отображении страниц документа. Это свойство игнорируется при рендеринге фигур в изображения.

### Примеры

Показывает, как извлекать страницы на основе точных диапазонов страниц.

```csharp
Document doc = new Document(MyDir + "Images.docx");

ImageSaveOptions imageOptions = new ImageSaveOptions(SaveFormat.Tiff);
PageSet pageSet = new PageSet(new PageRange(1, 1), new PageRange(2, 3), new PageRange(1, 3),
    new PageRange(2, 4), new PageRange(1, 1));

imageOptions.PageSet = pageSet;
doc.Save(ArtifactsDir + "ImageSaveOptions.ExportVariousPageRanges.tiff", imageOptions);
```

Показывает, как преобразовать каждую страницу документа в отдельное изображение TIFF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Page 1.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 2.");
builder.InsertImage(ImageDir + "Logo.jpg");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 3.");

// Создаем объект "ImageSaveOptions", который мы можем передать в метод "Сохранить" документа
// чтобы изменить способ, которым этот метод преобразует документ в изображение.
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Tiff);

for (int i = 0; i < doc.PageCount; i++)
{
    // Устанавливаем в свойство "PageSet" номер первой страницы из
    // с которого начать рендеринг документа.
    options.PageSet = new PageSet(i);

    doc.Save(ArtifactsDir + $"ImageSaveOptions.PageByPage.{i + 1}.tiff", options);
}
```

Показывает, как указать, какая страница документа должна отображаться как изображение.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
builder.Writeln("Hello world! This is page 1.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("This is page 3.");

Assert.AreEqual(3, doc.PageCount);

// Когда мы сохраняем документ как изображение, Aspose.Words по умолчанию отображает только первую страницу.
// Мы можем передать объект SaveOptions, чтобы указать другую страницу для отображения.
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Gif);

// Визуализировать каждую страницу документа в отдельный файл изображения.
for (int i = 1; i <= doc.PageCount; i++)
{
    saveOptions.PageSet = new PageSet(1);

    doc.Save(ArtifactsDir + $"ImageSaveOptions.PageIndex.Page {i}.gif", saveOptions);
}
```

Показывает, как преобразовать одну страницу из документа в изображение JPEG.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Page 1.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 2.");
builder.InsertImage(ImageDir + "Logo.jpg");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 3.");

// Создаем объект "ImageSaveOptions", который мы можем передать в метод "Сохранить" документа
// чтобы изменить способ, которым этот метод преобразует документ в изображение.
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

// Установите для "PageSet" значение "1", чтобы выбрать вторую страницу через
// отсчитываемый от нуля индекс, с которого начинается рендеринг документа.
options.PageSet = new PageSet(1);

// Когда мы сохраняем документ в формате JPEG, Aspose.Words отображает только одну страницу.
// Это изображение будет содержать одну страницу, начиная со второй страницы,
// которая будет просто второй страницей исходного документа.
doc.Save(ArtifactsDir + "ImageSaveOptions.OnePage.jpg", options);
```

### Смотрите также

* class [PageSet](../../pageset/)
* class [ImageSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../imagesaveoptions/)
* сборка [Aspose.Words](../../../)


