---
title: Table.AllowOverlap
second_title: Справочник по API Aspose.Words для .NET
description: Table свойство. Определяет должна ли плавающая таблица позволять другим плавающим объектам в документе перекрывать свои экстенты при отображении. Значение по умолчаниюистинный .
type: docs
weight: 70
url: /ru/net/aspose.words.tables/table/allowoverlap/
---
## Table.AllowOverlap property

Определяет, должна ли плавающая таблица позволять другим плавающим объектам в документе перекрывать свои экстенты при отображении. Значение по умолчанию:`истинный` .

```csharp
public bool AllowOverlap { get; }
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

* class [Table](../)
* пространство имен [Aspose.Words.Tables](../../table/)
* сборка [Aspose.Words](../../../)


