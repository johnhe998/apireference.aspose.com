---
title: BuiltInDocumentProperties.Thumbnail
second_title: Справочник по API Aspose.Words для .NET
description: BuiltInDocumentProperties свойство. Получает или задает миниатюру документа.
type: docs
weight: 280
url: /ru/net/aspose.words.properties/builtindocumentproperties/thumbnail/
---
## BuiltInDocumentProperties.Thumbnail property

Получает или задает миниатюру документа.

```csharp
public byte[] Thumbnail { get; set; }
```

### Примечания

На данный момент это свойство используется только при экспорте документа в ePub, он не читается и не записывается в документы других форматов.

В это свойство можно установить изображение произвольного формата, но формат проверяется при экспорте. InvalidOperationException выдается, если изображение недействительно или его формат не поддерживается для определенного формата документа .

Для публикации ePub можно использовать только изображения в формате gif, jpeg и png.

### Примеры

Показывает, как добавить миниатюру к документу, который мы сохраняем как Epub.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Если мы сохраним документ, свойство "Thumbnail" которого содержит данные изображения, которые мы добавили, как Epub,
// читатель, открывший этот документ, может отобразить изображение перед первой страницей.
BuiltInDocumentProperties properties = doc.BuiltInDocumentProperties;

byte[] thumbnailBytes = File.ReadAllBytes(ImageDir + "Logo.jpg");
properties.Thumbnail = thumbnailBytes;

doc.Save(ArtifactsDir + "DocumentProperties.Thumbnail.epub");

// Мы можем извлечь эскиз документа и сохранить его в локальной файловой системе.
DocumentProperty thumbnail = doc.BuiltInDocumentProperties["Thumbnail"];
File.WriteAllBytes(ArtifactsDir + "DocumentProperties.Thumbnail.gif", thumbnail.ToByteArray());
```

### Смотрите также

* class [BuiltInDocumentProperties](../)
* пространство имен [Aspose.Words.Properties](../../builtindocumentproperties/)
* сборка [Aspose.Words](../../../)


