---
title: Document.Clone
second_title: Справочник по API Aspose.Words для .NET
description: Document метод. Выполняет глубокую копиюDocument .
type: docs
weight: 530
url: /ru/net/aspose.words/document/clone/
---
## Document.Clone method

Выполняет глубокую копию[`Document`](../) .

```csharp
public Document Clone()
```

### Возвращаемое значение

Клонированный документ.

### Примеры

Показывает, как глубоко клонировать документ.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Hello world!");

// Клонирование создаст новый документ с тем же содержимым, что и исходный,
// но с уникальной копией каждого узла исходного документа.
Document clone = doc.Clone();

Assert.AreEqual(doc.FirstSection.Body.FirstParagraph.Runs[0].GetText(), 
    clone.FirstSection.Body.FirstParagraph.Runs[0].Text);
Assert.AreNotEqual(doc.FirstSection.Body.FirstParagraph.Runs[0].GetHashCode(),
    clone.FirstSection.Body.FirstParagraph.Runs[0].GetHashCode());
```

### Смотрите также

* class [Document](../)
* пространство имен [Aspose.Words](../../document/)
* сборка [Aspose.Words](../../../)


