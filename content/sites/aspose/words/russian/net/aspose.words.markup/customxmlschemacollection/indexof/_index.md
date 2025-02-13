---
title: CustomXmlSchemaCollection.IndexOf
second_title: Справочник по API Aspose.Words для .NET
description: CustomXmlSchemaCollection метод. Возвращает отсчитываемый от нуля индекс указанного значения в коллекции.
type: docs
weight: 70
url: /ru/net/aspose.words.markup/customxmlschemacollection/indexof/
---
## CustomXmlSchemaCollection.IndexOf method

Возвращает отсчитываемый от нуля индекс указанного значения в коллекции.

```csharp
public int IndexOf(string value)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| value | String | Значение с учетом регистра для поиска. |

### Возвращаемое значение

Индекс с отсчетом от нуля. Отрицательное значение, если не найдено.

### Примеры

Показывает, как работать с коллекцией схем XML.

```csharp
Document doc = new Document();

string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Hello, World!</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);

// Добавляем ассоциацию XML-схемы.
xmlPart.Schemas.Add("http://www.w3.org/2001/XMLSchema");

// Клонировать коллекцию ассоциаций схемы XML пользовательской части XML,
// а затем добавить пару новых схем в клон.
CustomXmlSchemaCollection schemas = xmlPart.Schemas.Clone();
schemas.Add("http://www.w3.org/2001/XMLSchema-instance");
schemas.Add("http://schemas.microsoft.com/office/2006/metadata/contentType");

Assert.AreEqual(3, schemas.Count);
Assert.AreEqual(2, schemas.IndexOf("http://schemas.microsoft.com/office/2006/metadata/contentType"));

// Перечисляем схемы и печатаем каждый элемент.
using (IEnumerator<string> enumerator = schemas.GetEnumerator())
{
    while (enumerator.MoveNext())
        Console.WriteLine(enumerator.Current);
}

// Ниже приведены три способа удаления схем из коллекции.
// 1 - Удалить схему по индексу:
schemas.RemoveAt(2);

// 2 - Удалить схему по значению:
schemas.Remove("http://www.w3.org/2001/XMLSchema");

// 3 - Используйте метод "Очистить", чтобы сразу очистить коллекцию.
schemas.Clear();

Assert.AreEqual(0, schemas.Count);
```

### Смотрите также

* class [CustomXmlSchemaCollection](../)
* пространство имен [Aspose.Words.Markup](../../customxmlschemacollection/)
* сборка [Aspose.Words](../../../)


