---
title: Class ThumbnailGeneratingOptions
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Rendering.ThumbnailGeneratingOptions сорт. Может использоваться для указания дополнительных параметров при создании миниатюры для документа.
type: docs
weight: 4340
url: /ru/net/aspose.words.rendering/thumbnailgeneratingoptions/
---
## ThumbnailGeneratingOptions class

Может использоваться для указания дополнительных параметров при создании миниатюры для документа.

```csharp
public class ThumbnailGeneratingOptions
```

## Конструкторы

| Имя | Описание |
| --- | --- |
| [ThumbnailGeneratingOptions](thumbnailgeneratingoptions/)() | Конструктор по умолчанию. |

## Характеристики

| Имя | Описание |
| --- | --- |
| [GenerateFromFirstPage](../../aspose.words.rendering/thumbnailgeneratingoptions/generatefromfirstpage/) { get; set; } | Указывает, следует ли создавать миниатюру из первой страницы документа или первого изображения. |
| [ThumbnailSize](../../aspose.words.rendering/thumbnailgeneratingoptions/thumbnailsize/) { get; set; } | Размер сгенерированного эскиза в пикселях. По умолчанию 600x900. |

### Примечания

Пользователь может вызывать метод[`UpdateThumbnail`](../../aspose.words/document/updatethumbnail/) для создания [`Thumbnail`](../../aspose.words.properties/builtindocumentproperties/thumbnail/) для документа.

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

* пространство имен [Aspose.Words.Rendering](../../aspose.words.rendering/)
* сборка [Aspose.Words](../../)


