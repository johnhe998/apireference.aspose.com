---
title: BuiltInDocumentProperties.Title
second_title: Справочник по API Aspose.Words для .NET
description: BuiltInDocumentProperties свойство. Получает или задает заголовок документа.
type: docs
weight: 290
url: /ru/net/aspose.words.properties/builtindocumentproperties/title/
---
## BuiltInDocumentProperties.Title property

Получает или задает заголовок документа.

```csharp
public string Title { get; set; }
```

### Примеры

Показывает, как работать со встроенными свойствами документа в категории «Описание».

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
BuiltInDocumentProperties properties = doc.BuiltInDocumentProperties;

// Ниже приведены четыре встроенных свойства документа с полями, которые могут отображать свои значения в теле документа.
// 1 - свойство "Автор", которое мы можем отобразить с помощью поля АВТОР:
properties.Author = "John Doe";
builder.Write("Author:\t");
builder.InsertField(FieldType.FieldAuthor, true);

// 2 - свойство "Title", которое мы можем отобразить с помощью поля TITLE:
properties.Title = "John's Document";
builder.Write("\nDoc title:\t");
builder.InsertField(FieldType.FieldTitle, true);

// 3 - свойство "Тема", которое мы можем отобразить с помощью поля SUBJECT:
properties.Subject = "My subject";
builder.Write("\nSubject:\t");
builder.InsertField(FieldType.FieldSubject, true);

// 4 - свойство "Комментарии", которое мы можем отобразить с помощью поля КОММЕНТАРИИ:
properties.Comments = $"This is {properties.Author}'s document about {properties.Subject}";
builder.Write("\nComments:\t\"");
builder.InsertField(FieldType.FieldComments, true);
builder.Write("\"");

// У встроенного свойства "Категория" нет поля, которое может отображать его значение.
properties.Category = "My category";

// Мы можем установить несколько ключевых слов для документа, разделив строковое значение свойства «Ключевые слова» точкой с запятой.
properties.Keywords = "Tag 1; Tag 2; Tag 3";

// Мы можем щелкнуть правой кнопкой мыши этот документ в проводнике Windows и найти эти свойства в «Свойствах» -> "Подробности".
// Встроенное свойство "Автор" находится в группе "Происхождение", а остальные - в группе "Описание".
doc.Save(ArtifactsDir + "DocumentProperties.Description.docx");
```

### Смотрите также

* class [BuiltInDocumentProperties](../)
* пространство имен [Aspose.Words.Properties](../../builtindocumentproperties/)
* сборка [Aspose.Words](../../../)


