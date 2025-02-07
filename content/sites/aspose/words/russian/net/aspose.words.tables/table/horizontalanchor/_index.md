---
title: Table.HorizontalAnchor
second_title: Справочник по API Aspose.Words для .NET
description: Table свойство. Получает базовый объект из которого должно быть рассчитано горизонтальное позиционирование плавающей таблицы. Значение по умолчаниюColumn .
type: docs
weight: 170
url: /ru/net/aspose.words.tables/table/horizontalanchor/
---
## Table.HorizontalAnchor property

Получает базовый объект, из которого должно быть рассчитано горизонтальное позиционирование плавающей таблицы. Значение по умолчанию:Column .

```csharp
public RelativeHorizontalPosition HorizontalAnchor { get; set; }
```

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

* enum [RelativeHorizontalPosition](../../../aspose.words.drawing/relativehorizontalposition/)
* class [Table](../)
* пространство имен [Aspose.Words.Tables](../../table/)
* сборка [Aspose.Words](../../../)


