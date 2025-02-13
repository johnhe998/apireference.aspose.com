---
title: CompareOptions.Granularity
second_title: Справочник по API Aspose.Words для .NET
description: CompareOptions свойство. Указывает отслеживаются ли изменения по символам или по словам. Значение по умолчаниюWordLevel .
type: docs
weight: 20
url: /ru/net/aspose.words.comparing/compareoptions/granularity/
---
## CompareOptions.Granularity property

Указывает, отслеживаются ли изменения по символам или по словам. Значение по умолчанию:WordLevel .

```csharp
public Granularity Granularity { get; set; }
```

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

* enum [Granularity](../../granularity/)
* class [CompareOptions](../)
* пространство имен [Aspose.Words.Comparing](../../compareoptions/)
* сборка [Aspose.Words](../../../)


