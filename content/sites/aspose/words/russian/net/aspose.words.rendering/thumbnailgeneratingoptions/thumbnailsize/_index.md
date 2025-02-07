---
title: ThumbnailGeneratingOptions.ThumbnailSize
second_title: Справочник по API Aspose.Words для .NET
description: ThumbnailGeneratingOptions свойство. Размер сгенерированного эскиза в пикселях. По умолчанию 600x900.
type: docs
weight: 30
url: /ru/net/aspose.words.rendering/thumbnailgeneratingoptions/thumbnailsize/
---
## ThumbnailGeneratingOptions.ThumbnailSize property

Размер сгенерированного эскиза в пикселях. По умолчанию 600x900.

```csharp
public Size ThumbnailSize { get; set; }
```

### Примеры

Показывает, как обновить миниатюру документа.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");
builder.InsertImage(ImageDir + "Logo.jpg");

// Существует два способа установки миниатюры при сохранении документа в формате .epub.
// 1 - Использовать первую страницу документа:
doc.UpdateThumbnail();
doc.Save(ArtifactsDir + "Document.UpdateThumbnail.FirstPage.epub");

// 2 - Использовать первое изображение, найденное в документе:
ThumbnailGeneratingOptions options = new ThumbnailGeneratingOptions();
options.ThumbnailSize = new Size(400, 400);
options.GenerateFromFirstPage = false;

doc.UpdateThumbnail(options);
doc.Save(ArtifactsDir + "Document.UpdateThumbnail.FirstImage.epub");
```

### Смотрите также

* class [ThumbnailGeneratingOptions](../)
* пространство имен [Aspose.Words.Rendering](../../thumbnailgeneratingoptions/)
* сборка [Aspose.Words](../../../)


