---
title: Class BaseWebExtensionCollectionT
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.WebExtensions.BaseWebExtensionCollection1T сорт. Базовый класс дляTaskPaneCollection WebExtensionBindingCollection  WebExtensionPropertyCollection а такжеWebExtensionReferenceCollection коллекции.
type: docs
weight: 6390
url: /ru/net/aspose.words.webextensions/basewebextensioncollection-1/
---
## BaseWebExtensionCollection&lt;T&gt; class

Базовый класс для[`TaskPaneCollection`](../taskpanecollection/) ,[`WebExtensionBindingCollection`](../webextensionbindingcollection/) , [`WebExtensionPropertyCollection`](../webextensionpropertycollection/) а также[`WebExtensionReferenceCollection`](../webextensionreferencecollection/) коллекции.

```csharp
public abstract class BaseWebExtensionCollection<T> : IEnumerable<T>
    where T : class
```

| Параметр | Описание |
| --- | --- |
| T | Тип предмета коллекции. |

## Характеристики

| Имя | Описание |
| --- | --- |
| [Count](../../aspose.words.webextensions/basewebextensioncollection-1/count/) { get; } | Получает количество элементов, содержащихся в коллекции. |
| [Item](../../aspose.words.webextensions/basewebextensioncollection-1/item/) { get; set; } | Получает или задает элемент по указанному индексу. |

## Методы

| Имя | Описание |
| --- | --- |
| [Add](../../aspose.words.webextensions/basewebextensioncollection-1/add/)(T) | Добавляет указанный элемент в коллекцию. |
| [Clear](../../aspose.words.webextensions/basewebextensioncollection-1/clear/)() | Удаляет все элементы из коллекции. |
| [GetEnumerator](../../aspose.words.webextensions/basewebextensioncollection-1/getenumerator/)() | Возвращает перечислитель, который может выполнять итерацию по коллекции. |
| [Remove](../../aspose.words.webextensions/basewebextensioncollection-1/remove/)(int) | Удаляет элемент с указанным индексом из коллекции. |

### Примеры

Показывает, как работать с коллекцией веб-расширений документа.

```csharp
Document doc = new Document(MyDir + "Web extension.docx");

Assert.AreEqual(1, doc.WebExtensionTaskPanes.Count);

// Вывести все свойства веб-расширения документа.
WebExtensionPropertyCollection webExtensionPropertyCollection = doc.WebExtensionTaskPanes[0].WebExtension.Properties;
using (IEnumerator<WebExtensionProperty> enumerator = webExtensionPropertyCollection.GetEnumerator())
{
    while (enumerator.MoveNext())
    {
        WebExtensionProperty webExtensionProperty = enumerator.Current;
        Console.WriteLine($"Binding name: {webExtensionProperty.Name}; Binding value: {webExtensionProperty.Value}");
    }
}

// Удалить веб-расширение.
doc.WebExtensionTaskPanes.Remove(0);

Assert.AreEqual(0, doc.WebExtensionTaskPanes.Count);
```

### Смотрите также

* пространство имен [Aspose.Words.WebExtensions](../../aspose.words.webextensions/)
* сборка [Aspose.Words](../../)


