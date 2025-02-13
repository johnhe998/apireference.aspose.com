---
title: ShapeBase.MarkupLanguage
second_title: Справочник по API Aspose.Words для .NET
description: ShapeBase свойство. Получает язык разметки используемый для этого графического объекта.
type: docs
weight: 370
url: /ru/net/aspose.words.drawing/shapebase/markuplanguage/
---
## ShapeBase.MarkupLanguage property

Получает язык разметки, используемый для этого графического объекта.

```csharp
public ShapeMarkupLanguage MarkupLanguage { get; }
```

### Примеры

Показывает, как проверить размер фигуры и язык разметки.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertImage(ImageDir + "Transparent background logo.png");

Assert.AreEqual(ShapeMarkupLanguage.Dml, shape.MarkupLanguage);
Assert.AreEqual(new SizeF(300, 300), shape.SizeInPoints);
```

### Смотрите также

* enum [ShapeMarkupLanguage](../../shapemarkuplanguage/)
* class [ShapeBase](../)
* пространство имен [Aspose.Words.Drawing](../../shapebase/)
* сборка [Aspose.Words](../../../)


