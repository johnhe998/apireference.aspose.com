---
title: FieldCollection.RemoveAt
second_title: Справочник по API Aspose.Words для .NET
description: FieldCollection метод. Удаляет поле с указанным индексом из этой коллекции и из документа.
type: docs
weight: 60
url: /ru/net/aspose.words.fields/fieldcollection/removeat/
---
## FieldCollection.RemoveAt method

Удаляет поле с указанным индексом из этой коллекции и из документа.

```csharp
public void RemoveAt(int index)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| index | Int32 | Индекс в коллекции. |

### Примеры

Показывает, как удалить поля из коллекции полей.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(" DATE \\@ \"dddd, d MMMM yyyy\" ");
builder.InsertField(" TIME ");
builder.InsertField(" REVNUM ");
builder.InsertField(" AUTHOR  \"John Doe\" ");
builder.InsertField(" SUBJECT \"My Subject\" ");
builder.InsertField(" QUOTE \"Hello world!\" ");
doc.UpdateFields();

FieldCollection fields = doc.Range.Fields;

Assert.AreEqual(6, fields.Count);

// Ниже приведены четыре способа удаления полей из набора полей.
// 1 - Получить поле для удаления самого себя:
fields[0].Remove();
Assert.AreEqual(5, fields.Count);

// 2 - Получить коллекцию для удаления поля, которое мы передаем в метод ее удаления:
Field lastField = fields[3];
fields.Remove(lastField);
Assert.AreEqual(4, fields.Count);

// 3 - Удалить поле из коллекции по индексу:
fields.RemoveAt(2);
Assert.AreEqual(3, fields.Count);

// 4 - Удалить сразу все поля из коллекции:
fields.Clear();
Assert.AreEqual(0, fields.Count);
```

### Смотрите также

* class [FieldCollection](../)
* пространство имен [Aspose.Words.Fields](../../fieldcollection/)
* сборка [Aspose.Words](../../../)


