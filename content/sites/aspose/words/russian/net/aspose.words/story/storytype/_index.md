---
title: Story.StoryType
second_title: Справочник по API Aspose.Words для .NET
description: Story свойство. Получает тип этой истории.
type: docs
weight: 40
url: /ru/net/aspose.words/story/storytype/
---
## Story.StoryType property

Получает тип этой истории.

```csharp
public StoryType StoryType { get; }
```

### Примеры

Показывает, как удалить все фигуры из узла.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Используйте DocumentBuilder для вставки фигуры. Это встроенная форма,
// у которого есть родительский абзац, который является дочерним узлом тела первого раздела.
builder.InsertShape(ShapeType.Cube, 100.0, 100.0);

Assert.AreEqual(1, doc.GetChildNodes(NodeType.Shape, true).Count);

// Мы можем удалить все фигуры из дочерних абзацев этого тела.
Assert.AreEqual(StoryType.MainText, doc.FirstSection.Body.StoryType);
doc.FirstSection.Body.DeleteShapes();

Assert.AreEqual(0, doc.GetChildNodes(NodeType.Shape, true).Count);
```

### Смотрите также

* enum [StoryType](../../storytype/)
* class [Story](../)
* пространство имен [Aspose.Words](../../story/)
* сборка [Aspose.Words](../../../)


