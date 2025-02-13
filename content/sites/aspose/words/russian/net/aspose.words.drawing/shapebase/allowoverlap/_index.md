---
title: ShapeBase.AllowOverlap
second_title: Справочник по API Aspose.Words для .NET
description: ShapeBase свойство. Получает или задает значение указывающее может ли эта фигура перекрывать другие фигуры.
type: docs
weight: 10
url: /ru/net/aspose.words.drawing/shapebase/allowoverlap/
---
## ShapeBase.AllowOverlap property

Получает или задает значение, указывающее, может ли эта фигура перекрывать другие фигуры.

```csharp
public bool AllowOverlap { get; set; }
```

### Примечания

Это свойство влияет на поведение фигуры в Microsoft Word. Aspose.Words игнорирует значение этого свойства.

Это свойство применимо только к фигурам верхнего уровня.

Значение по умолчанию **истинный**.

### Примеры

Показывает, как работать со свойствами плавающих таблиц.

```csharp
Document doc = new Document(MyDir + "Table wrapped by text.docx");

Table table = doc.FirstSection.Body.Tables[0];

if (table.TextWrapping == TextWrapping.Around)
{
    Assert.AreEqual(RelativeHorizontalPosition.Margin, table.HorizontalAnchor);
    Assert.AreEqual(RelativeVerticalPosition.Paragraph, table.VerticalAnchor);
    Assert.AreEqual(false, table.AllowOverlap);

    // Только Margin, Page, Column доступны в RelativeHorizontalPosition для установщика HorizontalAnchor.
    // ArgumentException будет сгенерировано для любых других значений.
    table.HorizontalAnchor = RelativeHorizontalPosition.Column;

    // Только Margin, Page, Paragraph доступны в RelativeVerticalPosition для установщика VerticalAnchor.
    // ArgumentException будет сгенерировано для любых других значений.
    table.VerticalAnchor = RelativeVerticalPosition.Page;
}
```

### Смотрите также

* class [ShapeBase](../)
* пространство имен [Aspose.Words.Drawing](../../shapebase/)
* сборка [Aspose.Words](../../../)


