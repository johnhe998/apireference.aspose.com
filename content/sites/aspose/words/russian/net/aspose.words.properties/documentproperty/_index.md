---
title: Class DocumentProperty
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Properties.DocumentProperty сорт. Представляет пользовательское или встроенное свойство документа.
type: docs
weight: 4220
url: /ru/net/aspose.words.properties/documentproperty/
---
## DocumentProperty class

Представляет пользовательское или встроенное свойство документа.

```csharp
public class DocumentProperty
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [IsLinkToContent](../../aspose.words.properties/documentproperty/islinktocontent/) { get; } | Показывает, связано ли это свойство с контентом или нет. |
| [LinkSource](../../aspose.words.properties/documentproperty/linksource/) { get; } | Получает источник связанного пользовательского свойства документа. |
| [Name](../../aspose.words.properties/documentproperty/name/) { get; } | Возвращает имя свойства. |
| [Type](../../aspose.words.properties/documentproperty/type/) { get; } | Получает тип данных свойства. |
| [Value](../../aspose.words.properties/documentproperty/value/) { get; set; } | Получает или задает значение свойства. |

## Методы

| Имя | Описание |
| --- | --- |
| [ToBool](../../aspose.words.properties/documentproperty/tobool/)() | Возвращает значение свойства как bool. |
| [ToByteArray](../../aspose.words.properties/documentproperty/tobytearray/)() | Возвращает значение свойства в виде массива байтов. |
| [ToDateTime](../../aspose.words.properties/documentproperty/todatetime/)() | Возвращает значение свойства в формате DateTime в формате UTC. |
| [ToDouble](../../aspose.words.properties/documentproperty/todouble/)() | Возвращает значение свойства как двойное. |
| [ToInt](../../aspose.words.properties/documentproperty/toint/)() | Возвращает значение свойства в виде целого числа. |
| override [ToString](../../aspose.words.properties/documentproperty/tostring/)() | Возвращает значение свойства в виде строки, отформатированной в соответствии с текущей локалью. |

### Примеры

Показывает, как работать со встроенными свойствами документа.

```csharp
Document doc = new Document(MyDir + "Properties.docx");

// Объект «Документ» содержит некоторые метаданные в своих членах.
Console.WriteLine($"Document filename:\n\t \"{doc.OriginalFileName}\"");

// Документ также хранит метаданные в своих встроенных свойствах.
// Каждое встроенное свойство является членом объекта «BuiltInDocumentProperties» документа.
Console.WriteLine("Built-in Properties:");
foreach (DocumentProperty docProperty in doc.BuiltInDocumentProperties)
{
    Console.WriteLine(docProperty.Name);
    Console.WriteLine($"\tType:\t{docProperty.Type}");

    // Некоторые свойства могут хранить несколько значений.
    if (docProperty.Value is ICollection<object>)
    {
        foreach (object value in docProperty.Value as ICollection<object>)
            Console.WriteLine($"\tValue:\t\"{value}\"");
    }
    else
    {
        Console.WriteLine($"\tValue:\t\"{docProperty.Value}\"");
    }
}
```

### Смотрите также

* class [DocumentPropertyCollection](../documentpropertycollection/)
* пространство имен [Aspose.Words.Properties](../../aspose.words.properties/)
* сборка [Aspose.Words](../../)


