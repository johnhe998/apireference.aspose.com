---
title: CustomPart.RelationshipType
second_title: Справочник по API Aspose.Words для .NET
description: CustomPart свойство. Получает или задает тип отношения между родительской частью и этой пользовательской частью.
type: docs
weight: 60
url: /ru/net/aspose.words.markup/custompart/relationshiptype/
---
## CustomPart.RelationshipType property

Получает или задает тип отношения между родительской частью и этой пользовательской частью.

```csharp
public string RelationshipType { get; set; }
```

### Примечания

Тип отношения для пользовательской части должен быть «неизвестным», например, тип пользовательского отношения, , а не один из типов отношений, определенных в ISO/IEC 29500.

Значение по умолчанию — пустая строка. Допустимое значение должно быть непустой строкой.

### Примеры

Показывает, как получить доступ к коллекции произвольных пользовательских частей документа.

```csharp
Document doc = new Document(MyDir + "Custom parts OOXML package.docx");

Assert.AreEqual(2, doc.PackageCustomParts.Count);

// Клонируем вторую часть, затем добавляем клон в коллекцию.
CustomPart clonedPart = doc.PackageCustomParts[1].Clone();
doc.PackageCustomParts.Add(clonedPart);
Assert.AreEqual(3, doc.PackageCustomParts.Count);

// Перечисляем коллекцию и печатаем каждую часть.
using (IEnumerator<CustomPart> enumerator = doc.PackageCustomParts.GetEnumerator())
{
    int index = 0;
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Part index {index}:");
        Console.WriteLine($"\tName:\t\t\t\t{enumerator.Current.Name}");
        Console.WriteLine($"\tContent type:\t\t{enumerator.Current.ContentType}");
        Console.WriteLine($"\tRelationship type:\t{enumerator.Current.RelationshipType}");
        Console.WriteLine(enumerator.Current.IsExternal ?
            "\tSourced from outside the document" :
            $"\tStored within the document, length: {enumerator.Current.Data.Length} bytes");
        index++;
    }
}

// Мы можем удалить элементы из этой коллекции по отдельности или все сразу.
doc.PackageCustomParts.RemoveAt(2);

Assert.AreEqual(2, doc.PackageCustomParts.Count);

doc.PackageCustomParts.Clear();

Assert.AreEqual(0, doc.PackageCustomParts.Count);
```

### Смотрите также

* class [CustomPart](../)
* пространство имен [Aspose.Words.Markup](../../custompart/)
* сборка [Aspose.Words](../../../)


