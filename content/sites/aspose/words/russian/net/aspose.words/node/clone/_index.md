---
title: Node.Clone
second_title: Справочник по API Aspose.Words для .NET
description: Node метод. Создает дубликат узла.
type: docs
weight: 100
url: /ru/net/aspose.words/node/clone/
---
## Node.Clone method

Создает дубликат узла.

```csharp
public Node Clone(bool isCloneChildren)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| isCloneChildren | Boolean | Значение true, чтобы рекурсивно клонировать поддерево в указанном узле; false, чтобы клонировать только сам узел. |

### Возвращаемое значение

Клонированный узел.

### Примечания

Этот метод служит конструктором копирования для узлов. Клонированный узел не имеет родителя, но принадлежит к тому же документу, что и исходный узел.

Этот метод всегда выполняет глубокую копию узла.isCloneДети Параметр указывает, следует ли выполнять копирование всех дочерних узлов.

### Примеры

Показывает, как клонировать составной узел.

```csharp
Document doc = new Document();
Paragraph para = doc.FirstSection.Body.FirstParagraph;
para.AppendChild(new Run(doc, "Hello world!"));

// Ниже приведены два способа клонирования составного узла.
// 1 - Создать клон узла, а также создать клон каждого из его дочерних узлов.
Node cloneWithChildren = para.Clone(true);

Assert.IsTrue(((CompositeNode)cloneWithChildren).HasChildNodes);
Assert.AreEqual("Hello world!", cloneWithChildren.GetText().Trim());

// 2 - Создать клон узла без дочерних элементов.
Node cloneWithoutChildren = para.Clone(false);

Assert.IsFalse(((CompositeNode)cloneWithoutChildren).HasChildNodes);
Assert.AreEqual(string.Empty, cloneWithoutChildren.GetText().Trim());
```

### Смотрите также

* class [Node](../)
* пространство имен [Aspose.Words](../../node/)
* сборка [Aspose.Words](../../../)


