---
title: Class PlainTextDocument
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.PlainTextDocument сорт. Позволяет извлекать текстовое представление содержимого документа.
type: docs
weight: 4190
url: /ru/net/aspose.words/plaintextdocument/
---
## PlainTextDocument class

Позволяет извлекать текстовое представление содержимого документа.

```csharp
public class PlainTextDocument
```

## Конструкторы

| Имя | Описание |
| --- | --- |
| [PlainTextDocument](plaintextdocument/#constructor)(Stream) | Создает простой текстовый документ из потока. Автоматически определяет формат файла. |
| [PlainTextDocument](plaintextdocument/#constructor_2)(string) | Создает простой текстовый документ из файла. Автоматически определяет формат файла. |
| [PlainTextDocument](plaintextdocument/#constructor_1)(Stream, LoadOptions) | Создает простой текстовый документ из потока. Позволяет указать дополнительные параметры, такие как пароль шифрования. |
| [PlainTextDocument](plaintextdocument/#constructor_3)(string, LoadOptions) | Создает простой текстовый документ из файла. Позволяет указать дополнительные параметры, такие как пароль шифрования. |

## Характеристики

| Имя | Описание |
| --- | --- |
| [BuiltInDocumentProperties](../../aspose.words/plaintextdocument/builtindocumentproperties/) { get; } | получает[`BuiltInDocumentProperties`](./builtindocumentproperties/) документа. |
| [CustomDocumentProperties](../../aspose.words/plaintextdocument/customdocumentproperties/) { get; } | получает[`CustomDocumentProperties`](./customdocumentproperties/) документа. |
| [Text](../../aspose.words/plaintextdocument/text/) { get; } | Получает текстовое содержимое документа, объединенного в виде строки. |

### Примеры

Показывает, как загрузить содержимое документа Microsoft Word в виде обычного текста.

```csharp
Document doc = new Document(); 
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

doc.Save(ArtifactsDir + "PlainTextDocument.Load.docx");

PlainTextDocument plaintext = new PlainTextDocument(ArtifactsDir + "PlainTextDocument.Load.docx");

Assert.AreEqual("Hello world!", plaintext.Text.Trim());
```

### Смотрите также

* пространство имен [Aspose.Words](../../aspose.words/)
* сборка [Aspose.Words](../../)


