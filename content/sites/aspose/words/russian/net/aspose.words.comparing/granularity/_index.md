---
title: Enum Granularity
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Comparing.Granularity перечисление. Задает степень детализации изменений для отслеживания при сравнении двух документов.
type: docs
weight: 280
url: /ru/net/aspose.words.comparing/granularity/
---
## Granularity enumeration

Задает степень детализации изменений для отслеживания при сравнении двух документов.

```csharp
public enum Granularity
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| CharLevel | `0` |  |
| WordLevel | `1` |  |

### Примеры

Показывает, чтобы указать степень детализации при сравнении документов.

```csharp
Document docA = new Document();
DocumentBuilder builderA = new DocumentBuilder(docA);
builderA.Writeln("Alpha Lorem ipsum dolor sit amet, consectetur adipiscing elit");

Document docB = new Document();
DocumentBuilder builderB = new DocumentBuilder(docB);
builderB.Writeln("Lorems ipsum dolor sit amet consectetur - \"adipiscing\" elit");

// Указываем, отслеживаются ли изменения
// по символу ('Granularity.CharLevel') или по слову ('Granularity.WordLevel').
Aspose.Words.Comparing.CompareOptions compareOptions = new Aspose.Words.Comparing.CompareOptions();
compareOptions.Granularity = granularity;

docA.Compare(docB, "author", DateTime.Now, compareOptions);

// Коллекция групп редакций первого документа содержит все различия между документами.
RevisionGroupCollection groups = docA.Revisions.Groups;
Assert.AreEqual(5, groups.Count);
```

### Смотрите также

* пространство имен [Aspose.Words.Comparing](../../aspose.words.comparing/)
* сборка [Aspose.Words](../../)


