---
title: Node.CustomNodeId
second_title: Справочник по API Aspose.Words для .NET
description: Node свойство. Указывает идентификатор пользовательского узла.
type: docs
weight: 10
url: /ru/net/aspose.words/node/customnodeid/
---
## Node.CustomNodeId property

Указывает идентификатор пользовательского узла.

```csharp
public int CustomNodeId { get; set; }
```

### Примечания

По умолчанию ноль.

Этот идентификатор можно установить и использовать произвольно. Например, как ключ для получения внешних данных.

Важное примечание: указанное значение не сохраняется в выходной файл и существует только в течение срока службы узла.

### Примеры

Показывает, как пройти через коллекцию дочерних узлов составного узла.

```csharp
Document doc = new Document();

// Добавьте два прогона и одну фигуру в качестве дочерних узлов в первый абзац этого документа.
Paragraph paragraph = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);
paragraph.AppendChild(new Run(doc, "Hello world! "));

Shape shape = new Shape(doc, ShapeType.Rectangle);
shape.Width = 200;
shape.Height = 200;
// Обратите внимание, что 'CustomNodeId' не сохраняется в выходной файл и существует только во время жизни узла.
shape.CustomNodeId = 100;
shape.WrapType = WrapType.Inline;
paragraph.AppendChild(shape);

paragraph.AppendChild(new Run(doc, "Hello again!"));

// Итерация по коллекции непосредственных дочерних элементов абзаца,
// и печатаем любые прогоны или формы, которые мы находим внутри.
NodeCollection children = paragraph.ChildNodes;

Assert.AreEqual(3, paragraph.ChildNodes.Count);

foreach (Node child in children)
    switch (child.NodeType)
    {
        case NodeType.Run:
            Console.WriteLine("Run contents:");
            Console.WriteLine($"\t\"{child.GetText().Trim()}\"");
            break;
        case NodeType.Shape:
            Shape childShape = (Shape)child;
            Console.WriteLine("Shape:");
            Console.WriteLine($"\t{childShape.ShapeType}, {childShape.Width}x{childShape.Height}");
    }
```

### Смотрите также

* class [Node](../)
* пространство имен [Aspose.Words](../../node/)
* сборка [Aspose.Words](../../../)


