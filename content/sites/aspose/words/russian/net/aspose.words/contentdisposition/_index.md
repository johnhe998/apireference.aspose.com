---
title: Enum ContentDisposition
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.ContentDisposition перечисление. Перечисляет различные способы представления документа в браузере клиента.
type: docs
weight: 330
url: /ru/net/aspose.words/contentdisposition/
---
## ContentDisposition enumeration

Перечисляет различные способы представления документа в браузере клиента.

```csharp
public enum ContentDisposition
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| Attachment | `0` | Отправить документ в браузер и предоставить возможность сохранить документ на диск или открыть в приложении , связанном с расширением документа. |
| Inline | `1` | Отправить документ в браузер и предоставить возможность сохранить документ на диск или открыть в браузере. |

### Примечания

Обратите внимание, что на фактическое поведение в браузере клиента может повлиять конфигурация безопасности браузера.

### Примеры

Показывает, как выполнить слияние почты, а затем сохранить документ в браузере клиента.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(" MERGEFIELD FullName ");
builder.InsertParagraph();
builder.InsertField(" MERGEFIELD Company ");
builder.InsertParagraph();
builder.InsertField(" MERGEFIELD Address ");
builder.InsertParagraph();
builder.InsertField(" MERGEFIELD City ");

doc.MailMerge.Execute(new string[] { "FullName", "Company", "Address", "City" },
    new object[] { "James Bond", "MI5 Headquarters", "Milbank", "London" });

// Отправляем документ в клиентский браузер.
Assert.That(() => doc.Save(response, "Artifacts/MailMerge.ExecuteArray.docx", ContentDisposition.Inline, null),
    Throws.TypeOf<ArgumentNullException>()); // Выброшено, потому что HttpResponse имеет значение null в тесте.

// Нам нужно будет закрыть этот ответ вручную, чтобы гарантировать, что мы не добавим лишний контент в документ после сохранения.
Assert.That(() => response.End(), Throws.TypeOf<NullReferenceException>());
```

### Смотрите также

* пространство имен [Aspose.Words](../../aspose.words/)
* сборка [Aspose.Words](../../)


