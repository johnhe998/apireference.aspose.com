---
title: FieldCollection.Item
second_title: Справочник по API Aspose.Words для .NET
description: FieldCollection свойство. Возвращает поле по указанному индексу.
type: docs
weight: 20
url: /ru/net/aspose.words.fields/fieldcollection/item/
---
## FieldCollection indexer

Возвращает поле по указанному индексу.

```csharp
public Field this[int index] { get; }
```

| Параметр | Описание |
| --- | --- |
| index | Индекс в коллекции. |

### Примечания

Индекс отсчитывается от нуля.

Отрицательные индексы разрешены и указывают на доступ из задней части коллекции. Например, -1 означает последний элемент, -2 означает предпоследний и так далее.

Если индекс больше или равен количеству элементов в списке, возвращается пустая ссылка.

Если индекс отрицательный и его абсолютное значение больше, чем количество элементов в списке, возвращается пустая ссылка.

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

* class [Field](../../field/)
* class [FieldCollection](../)
* пространство имен [Aspose.Words.Fields](../../fieldcollection/)
* сборка [Aspose.Words](../../../)


