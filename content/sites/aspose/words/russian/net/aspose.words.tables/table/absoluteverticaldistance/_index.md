---
title: Table.AbsoluteVerticalDistance
second_title: Справочник по API Aspose.Words для .NET
description: Table свойство. Получает или задает абсолютную вертикальную плавающую позицию таблицы указанную в свойствах таблицы в пунктах. Значение по умолчанию 0.
type: docs
weight: 30
url: /ru/net/aspose.words.tables/table/absoluteverticaldistance/
---
## Table.AbsoluteVerticalDistance property

Получает или задает абсолютную вертикальную плавающую позицию таблицы, указанную в свойствах таблицы, в пунктах. Значение по умолчанию: 0.

```csharp
public double AbsoluteVerticalDistance { get; set; }
```

### Примеры

Показывает, как задать расположение плавающих таблиц.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Table 1, cell 1");
builder.EndTable();
table.PreferredWidth = PreferredWidth.FromPoints(300);

// Установите положение таблицы в место на странице, например, в данном случае в правый нижний угол.
table.RelativeVerticalAlignment = VerticalAlignment.Bottom;
table.RelativeHorizontalAlignment = HorizontalAlignment.Right;

table = builder.StartTable();
builder.InsertCell();
builder.Write("Table 2, cell 1");
builder.EndTable();
table.PreferredWidth = PreferredWidth.FromPoints(300);

// Мы также можем установить горизонтальное и вертикальное смещение в пунктах от места абзаца, в которое мы вставили таблицу. 
table.AbsoluteVerticalDistance = 50;
table.AbsoluteHorizontalDistance = 100;

doc.Save(ArtifactsDir + "Table.ChangeFloatingTableProperties.docx");
```

### Смотрите также

* class [Table](../)
* пространство имен [Aspose.Words.Tables](../../table/)
* сборка [Aspose.Words](../../../)


