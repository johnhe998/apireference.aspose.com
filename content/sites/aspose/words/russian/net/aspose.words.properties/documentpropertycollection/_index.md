---
title: Class DocumentPropertyCollection
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Properties.DocumentPropertyCollection сорт. Базовый класс дляBuiltInDocumentProperties а такжеCustomDocumentProperties коллекции.
type: docs
weight: 4230
url: /ru/net/aspose.words.properties/documentpropertycollection/
---
## DocumentPropertyCollection class

Базовый класс для[`BuiltInDocumentProperties`](../builtindocumentproperties/) а также[`CustomDocumentProperties`](../customdocumentproperties/) коллекции.

```csharp
public abstract class DocumentPropertyCollection : IEnumerable<DocumentProperty>
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [Count](../../aspose.words.properties/documentpropertycollection/count/) { get; } | Получает количество элементов в коллекции. |
| [Item](../../aspose.words.properties/documentpropertycollection/item/) { get; } | Возвращает[`DocumentProperty`](../documentproperty/) объект по индексу. |
| virtual [Item](../../aspose.words.properties/documentpropertycollection/item/) { get; } | Возвращает[`DocumentProperty`](../documentproperty/) объект по имени свойства. |

## Методы

| Имя | Описание |
| --- | --- |
| [Clear](../../aspose.words.properties/documentpropertycollection/clear/)() | Удаляет все свойства из коллекции. |
| [Contains](../../aspose.words.properties/documentpropertycollection/contains/)(string) | Возвращает значение true, если свойство с указанным именем существует в коллекции. |
| [GetEnumerator](../../aspose.words.properties/documentpropertycollection/getenumerator/)() | Возвращает объект перечислителя, который можно использовать для перебора всех элементов в коллекции. |
| [IndexOf](../../aspose.words.properties/documentpropertycollection/indexof/)(string) | Получает индекс свойства по имени. |
| [Remove](../../aspose.words.properties/documentpropertycollection/remove/)(string) | Удаляет свойство с указанным именем из коллекции. |
| [RemoveAt](../../aspose.words.properties/documentpropertycollection/removeat/)(int) | Удаляет свойство по указанному индексу. |

### Примечания

Имена свойств нечувствительны к регистру.

Свойства в коллекции отсортированы в алфавитном порядке по имени.

### Примеры

Показывает, как работать с пользовательскими свойствами документа.

```csharp
Document doc = new Document();
CustomDocumentProperties properties = doc.CustomDocumentProperties;

Assert.AreEqual(0, properties.Count);

// Пользовательские свойства документа — это пары ключ-значение, которые мы можем добавить в документ.
properties.Add("Authorized", true);
properties.Add("Authorized By", "John Doe");
properties.Add("Authorized Date", DateTime.Today);
properties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
properties.Add("Authorized Amount", 123.45);

// Коллекция сортирует пользовательские свойства в алфавитном порядке.
Assert.AreEqual(1, properties.IndexOf("Authorized Amount"));
Assert.AreEqual(5, properties.Count);

// Распечатать каждое пользовательское свойство в документе.
using (IEnumerator<DocumentProperty> enumerator = properties.GetEnumerator())
{
    while (enumerator.MoveNext())
        Console.WriteLine($"Name: \"{enumerator.Current.Name}\"\n\tType: \"{enumerator.Current.Type}\"\n\tValue: \"{enumerator.Current.Value}\"");
}

// Отображение значения пользовательского свойства с использованием поля DOCPROPERTY.
DocumentBuilder builder = new DocumentBuilder(doc);
FieldDocProperty field = (FieldDocProperty)builder.InsertField(" DOCPROPERTY \"Authorized By\"");
field.Update();

Assert.AreEqual("John Doe", field.Result);

// Мы можем найти эти пользовательские свойства в Microsoft Word через «Файл» -> "Свойства" > "Дополнительные свойства" > "Обычай".
doc.Save(ArtifactsDir + "DocumentProperties.DocumentPropertyCollection.docx");

// Ниже приведены три способа удаления пользовательских свойств из документа.
// 1 - Удалить по индексу:
properties.RemoveAt(1);

Assert.False(properties.Contains("Authorized Amount"));
Assert.AreEqual(4, properties.Count);

// 2 - Удалить по имени:
properties.Remove("Authorized Revision");

Assert.False(properties.Contains("Authorized Revision"));
Assert.AreEqual(3, properties.Count);

// 3 - Очистить всю коллекцию сразу:
properties.Clear();

Assert.AreEqual(0, properties.Count);
```

### Смотрите также

* class [BuiltInDocumentProperties](../builtindocumentproperties/)
* class [CustomDocumentProperties](../customdocumentproperties/)
* class [DocumentProperty](../documentproperty/)
* пространство имен [Aspose.Words.Properties](../../aspose.words.properties/)
* сборка [Aspose.Words](../../)


