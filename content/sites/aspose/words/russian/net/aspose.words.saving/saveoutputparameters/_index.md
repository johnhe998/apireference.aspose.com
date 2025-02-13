---
title: Class SaveOutputParameters
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Saving.SaveOutputParameters сорт. Этот объект возвращается вызывающей стороне после сохранения документа и содержит дополнительную информацию которая была сгенерирована или рассчитана во время операции сохранения. Вызывающий может использовать или игнорировать этот объект.
type: docs
weight: 5310
url: /ru/net/aspose.words.saving/saveoutputparameters/
---
## SaveOutputParameters class

Этот объект возвращается вызывающей стороне после сохранения документа и содержит дополнительную информацию, которая была сгенерирована или рассчитана во время операции сохранения. Вызывающий может использовать или игнорировать этот объект.

```csharp
public class SaveOutputParameters
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [ContentType](../../aspose.words.saving/saveoutputparameters/contenttype/) { get; } | Возвращает строку Content-Type (тип интернет-медиа), которая определяет тип сохраненного документа. |

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

* пространство имен [Aspose.Words.Saving](../../aspose.words.saving/)
* сборка [Aspose.Words](../../)


