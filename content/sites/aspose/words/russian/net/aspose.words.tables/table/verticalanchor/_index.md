---
title: Table.VerticalAnchor
second_title: Справочник по API Aspose.Words для .NET
description: Table свойство. Получает базовый объект из которого должно быть рассчитано вертикальное позиционирование плавающей таблицы. Значение по умолчаниюMargin .
type: docs
weight: 340
url: /ru/net/aspose.words.tables/table/verticalanchor/
---
## Table.VerticalAnchor property

Получает базовый объект, из которого должно быть рассчитано вертикальное позиционирование плавающей таблицы. Значение по умолчанию:Margin .

```csharp
public RelativeVerticalPosition VerticalAnchor { get; set; }
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

* enum [RelativeVerticalPosition](../../../aspose.words.drawing/relativeverticalposition/)
* class [Table](../)
* пространство имен [Aspose.Words.Tables](../../table/)
* сборка [Aspose.Words](../../../)


