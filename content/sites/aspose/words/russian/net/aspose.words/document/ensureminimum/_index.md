---
title: Document.EnsureMinimum
second_title: Справочник по API Aspose.Words для .NET
description: Document метод. Если документ не содержит разделов создается один раздел с одним абзацем.
type: docs
weight: 560
url: /ru/net/aspose.words/document/ensureminimum/
---
## Document.EnsureMinimum method

Если документ не содержит разделов, создается один раздел с одним абзацем.

```csharp
public void EnsureMinimum()
```

### Примеры

Показывает, как убедиться, что документ содержит минимальный набор узлов, необходимый для редактирования его содержимого.

```csharp
// Вновь созданный документ содержит один дочерний раздел, который включает в себя одно дочернее тело и один дочерний абзац.
// Мы можем редактировать содержимое тела документа, добавляя в этот абзац такие узлы, как Runs или встроенные Shapes.
Document doc = new Document();
NodeCollection nodes = doc.GetChildNodes(NodeType.Any, true);

Assert.AreEqual(NodeType.Section, nodes[0].NodeType);
Assert.AreEqual(doc, nodes[0].ParentNode);

Assert.AreEqual(NodeType.Body, nodes[1].NodeType);
Assert.AreEqual(nodes[0], nodes[1].ParentNode);

Assert.AreEqual(NodeType.Paragraph, nodes[2].NodeType);
Assert.AreEqual(nodes[1], nodes[2].ParentNode);

// Это минимальный набор узлов, который нам нужен, чтобы иметь возможность редактировать документ.
// Мы больше не сможем редактировать документ, если удалим любой из них.
doc.RemoveAllChildren();

Assert.AreEqual(0, doc.GetChildNodes(NodeType.Any, true).Count);

// Вызовите этот метод, чтобы убедиться, что в документе есть хотя бы эти три узла, чтобы мы могли снова его отредактировать.
doc.EnsureMinimum();

Assert.AreEqual(NodeType.Section, nodes[0].NodeType);
Assert.AreEqual(NodeType.Body, nodes[1].NodeType);
Assert.AreEqual(NodeType.Paragraph, nodes[2].NodeType);

((Paragraph)nodes[2]).Runs.Add(new Run(doc, "Hello world!"));
```

### Смотрите также

* class [Document](../)
* пространство имен [Aspose.Words](../../document/)
* сборка [Aspose.Words](../../../)


