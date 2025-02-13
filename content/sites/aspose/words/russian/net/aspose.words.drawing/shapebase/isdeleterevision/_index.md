---
title: ShapeBase.IsDeleteRevision
second_title: Справочник по API Aspose.Words для .NET
description: ShapeBase свойство. Возвращает значение true если этот объект был удален в Microsoft Word при включенном отслеживании изменений.
type: docs
weight: 240
url: /ru/net/aspose.words.drawing/shapebase/isdeleterevision/
---
## ShapeBase.IsDeleteRevision property

Возвращает значение true, если этот объект был удален в Microsoft Word при включенном отслеживании изменений.

```csharp
public bool IsDeleteRevision { get; }
```

### Примеры

Показывает, как работать с формами изменений.

```csharp
Document doc = new Document();

Assert.False(doc.TrackRevisions);

// Вставьте встроенную фигуру без отслеживания ревизий, что сделает эту фигуру не ревизией любого вида.
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Начните отслеживать ревизии, а затем вставьте другую фигуру, которая будет ревизией.
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(2, shapes.Length);

shapes[0].Remove();

// Поскольку мы удалили эту фигуру во время отслеживания изменений,
// форма сохраняется в документе и считается удаленной ревизией.
// Принятие этой версии навсегда удалит фигуру, а отклонение сохранит ее в документе.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// И мы вставили другую фигуру, отслеживая изменения, так что эта форма будет считаться ревизией вставки.
// Принятие этой версии ассимилирует эту форму в документе как неизменяемую,
// и отказ от ревизии удалит эту форму навсегда.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

### Смотрите также

* class [ShapeBase](../)
* пространство имен [Aspose.Words.Drawing](../../shapebase/)
* сборка [Aspose.Words](../../../)


