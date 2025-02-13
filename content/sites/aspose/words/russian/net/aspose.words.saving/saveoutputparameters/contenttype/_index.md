---
title: SaveOutputParameters.ContentType
second_title: Справочник по API Aspose.Words для .NET
description: SaveOutputParameters свойство. Возвращает строку ContentType тип интернетмедиа которая определяет тип сохраненного документа.
type: docs
weight: 10
url: /ru/net/aspose.words.saving/saveoutputparameters/contenttype/
---
## SaveOutputParameters.ContentType property

Возвращает строку Content-Type (тип интернет-медиа), которая определяет тип сохраненного документа.

```csharp
public string ContentType { get; }
```

### Примеры

Показывает, как получить доступ к выходным параметрам операции сохранения документа.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// После сохранения документа мы можем получить доступ к типу Интернет-медиа (MIME-типу) только что созданного выходного документа.
SaveOutputParameters parameters = doc.Save(ArtifactsDir + "Document.SaveOutputParameters.doc");

Assert.AreEqual("application/msword", parameters.ContentType);

// Это свойство изменяется в зависимости от формата сохранения.
parameters = doc.Save(ArtifactsDir + "Document.SaveOutputParameters.pdf");

Assert.AreEqual("application/pdf", parameters.ContentType);
```

### Смотрите также

* class [SaveOutputParameters](../)
* пространство имен [Aspose.Words.Saving](../../saveoutputparameters/)
* сборка [Aspose.Words](../../../)


