---
title: CustomXmlPropertyCollection.GetEnumerator
second_title: Справочник по API Aspose.Words для .NET
description: CustomXmlPropertyCollection метод. Возвращает объект перечислителя который можно использовать для перебора всех элементов в коллекции.
type: docs
weight: 60
url: /ru/net/aspose.words.markup/customxmlpropertycollection/getenumerator/
---
## CustomXmlPropertyCollection.GetEnumerator method

Возвращает объект перечислителя, который можно использовать для перебора всех элементов в коллекции.

```csharp
public IEnumerator<CustomXmlProperty> GetEnumerator()
```

### Примеры

Показывает, как работать со свойствами смарт-тегов, чтобы получить подробную информацию о смарт-тегах.

```csharp
Document doc = new Document(MyDir + "Smart tags.doc");

// Смарт-тег появляется в документе, в котором Microsoft Word распознает часть своего текста как некую форму данных,
// таких как имя, дата или адрес, и преобразует их в гиперссылку, которая подчеркнута фиолетовой пунктирной линией.
// В Word 2003 мы можем включить смарт-теги через "Инструменты" -> "Параметры автозамены..." -> «Смарттеги».
// В нашем входном документе есть три объекта, которые Microsoft Word зарегистрировал как смарт-теги.
// Смарт-теги могут быть вложенными, поэтому в этой коллекции их больше.
SmartTag[] smartTags = doc.GetChildNodes(NodeType.SmartTag, true).OfType<SmartTag>().ToArray();

Assert.AreEqual(8, smartTags.Length);

// Элемент «Свойства» смарт-тега содержит его метаданные, которые будут разными для каждого типа смарт-тега.
// Свойства смарт-тега типа «дата» содержат его год, месяц и день.
CustomXmlPropertyCollection properties = smartTags[7].Properties;

Assert.AreEqual(4, properties.Count);

using (IEnumerator<CustomXmlProperty> enumerator = properties.GetEnumerator())
{
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Property name: {enumerator.Current.Name}, value: {enumerator.Current.Value}");
        Assert.AreEqual("", enumerator.Current.Uri);
    }
}

// Мы также можем получить доступ к свойствам различными способами, например, с помощью пары ключ-значение.
Assert.True(properties.Contains("Day"));
Assert.AreEqual("22", properties["Day"].Value);
Assert.AreEqual("2003", properties[2].Value);
Assert.AreEqual(1, properties.IndexOfKey("Month"));

// Ниже приведены три способа удаления элементов из коллекции свойств.
// 1 - Удалить по индексу:
properties.RemoveAt(3);

Assert.AreEqual(3, properties.Count);

// 2 - Удалить по имени:
properties.Remove("Year");

Assert.AreEqual(2, properties.Count);

// 3 - Очистить сразу всю коллекцию:
properties.Clear();

Assert.AreEqual(0, properties.Count);
```

### Смотрите также

* class [CustomXmlProperty](../../customxmlproperty/)
* class [CustomXmlPropertyCollection](../)
* пространство имен [Aspose.Words.Markup](../../customxmlpropertycollection/)
* сборка [Aspose.Words](../../../)


