---
title: DocumentPropertyCollection.Count
second_title: Справочник по API Aspose.Words для .NET
description: DocumentPropertyCollection свойство. Получает количество элементов в коллекции.
type: docs
weight: 10
url: /ru/net/aspose.words.properties/documentpropertycollection/count/
---
## DocumentPropertyCollection.Count property

Получает количество элементов в коллекции.

```csharp
public int Count { get; }
```

### Примеры

Показывает, как работать с пользовательскими свойствами документа.

```csharp
Document doc = new Document(MyDir + "Properties.docx");

// Каждый документ содержит набор настраиваемых свойств, которые, как и встроенные свойства, представляют собой пары ключ-значение.
// Документ имеет фиксированный список встроенных свойств. Пользователь создает все настраиваемые свойства. 
Assert.AreEqual("Value of custom document property", doc.CustomDocumentProperties["CustomProperty"].ToString());

doc.CustomDocumentProperties.Add("CustomProperty2", "Value of custom document property #2");

Console.WriteLine("Custom Properties:");
foreach (var customDocumentProperty in doc.CustomDocumentProperties)
{
    Console.WriteLine(customDocumentProperty.Name);
    Console.WriteLine($"\tType:\t{customDocumentProperty.Type}");
    Console.WriteLine($"\tValue:\t\"{customDocumentProperty.Value}\"");
}
```

### Смотрите также

* class [DocumentPropertyCollection](../)
* пространство имен [Aspose.Words.Properties](../../documentpropertycollection/)
* сборка [Aspose.Words](../../../)


