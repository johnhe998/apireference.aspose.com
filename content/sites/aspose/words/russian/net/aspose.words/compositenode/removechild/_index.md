---
title: CompositeNode.RemoveChild
second_title: Справочник по API Aspose.Words для .NET
description: CompositeNode метод. Удаляет указанный дочерний узел.
type: docs
weight: 180
url: /ru/net/aspose.words/compositenode/removechild/
---
## CompositeNode.RemoveChild method

Удаляет указанный дочерний узел.

```csharp
public Node RemoveChild(Node oldChild)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| oldChild | Node | Узел для удаления. |

### Возвращаемое значение

Удаленный узел.

### Примечания

Родительский элемент oldChild устанавливается равным нулю после удаления узла.

### Примеры

Показывает, как использовать методы Node и CompositeNode для удаления раздела перед последним разделом в документе.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1 text.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2 text.");

// Оба раздела являются родственными друг другу.
Section lastSection = (Section)doc.LastChild;
Section firstSection = (Section)lastSection.PreviousSibling;

// Удаляем раздел на основе родственного отношения с другим разделом.
if (lastSection.PreviousSibling != null)
    doc.RemoveChild(firstSection);

// Раздел, который мы удалили, был первым, оставив в документе только второй.
Assert.AreEqual("Section 2 text.", doc.GetText().Trim());
```

### Смотрите также

* class [Node](../../node/)
* class [CompositeNode](../)
* пространство имен [Aspose.Words](../../compositenode/)
* сборка [Aspose.Words](../../../)


