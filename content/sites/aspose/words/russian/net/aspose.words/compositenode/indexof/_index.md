---
title: CompositeNode.IndexOf
second_title: Справочник по API Aspose.Words для .NET
description: CompositeNode метод. Возвращает индекс указанного дочернего узла в массиве дочерних узлов.
type: docs
weight: 130
url: /ru/net/aspose.words/compositenode/indexof/
---
## CompositeNode.IndexOf method

Возвращает индекс указанного дочернего узла в массиве дочерних узлов.

```csharp
public int IndexOf(Node child)
```

### Примечания

Возвращает -1, если узел не найден среди дочерних узлов.

### Примеры

Показывает, как получить индекс данного дочернего узла от его родителя.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

Body body = doc.FirstSection.Body;

// Получить индекс последнего абзаца в теле первого раздела.
Assert.AreEqual(24, body.ChildNodes.IndexOf(body.LastParagraph));
```

### Смотрите также

* class [Node](../../node/)
* class [CompositeNode](../)
* пространство имен [Aspose.Words](../../compositenode/)
* сборка [Aspose.Words](../../../)


