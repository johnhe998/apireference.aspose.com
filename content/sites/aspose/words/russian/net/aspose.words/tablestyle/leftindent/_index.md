---
title: TableStyle.LeftIndent
second_title: Справочник по API Aspose.Words для .NET
description: TableStyle свойство. Получает или задает значение представляющее левый отступ таблицы.
type: docs
weight: 90
url: /ru/net/aspose.words/tablestyle/leftindent/
---
## TableStyle.LeftIndent property

Получает или задает значение, представляющее левый отступ таблицы.

```csharp
public double LeftIndent { get; set; }
```

### Примеры

Показывает, как установить положение таблицы.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ниже приведены два способа выравнивания таблицы по горизонтали.
// 1 — Используйте свойство «Выравнивание», чтобы выровнять его по месту на странице, например по центру:
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.Alignment = TableAlignment.Center;
tableStyle.Borders.Color = Color.Blue;
tableStyle.Borders.LineStyle = LineStyle.Single;

// Вставляем таблицу и применяем к ней созданный нами стиль.
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Aligned to the center of the page");
builder.EndTable();
table.PreferredWidth = PreferredWidth.FromPoints(300);

table.Style = tableStyle;

// 2 - Используйте "LeftIndent", чтобы указать отступ от левого поля страницы:
tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle2");
tableStyle.LeftIndent = 55;
tableStyle.Borders.Color = Color.Green;
tableStyle.Borders.LineStyle = LineStyle.Single;

table = builder.StartTable();
builder.InsertCell();
builder.Write("Aligned according to left indent");
builder.EndTable();
table.PreferredWidth = PreferredWidth.FromPoints(300);

table.Style = tableStyle;

doc.Save(ArtifactsDir + "Table.SetTableAlignment.docx");
```

### Смотрите также

* class [TableStyle](../)
* пространство имен [Aspose.Words](../../tablestyle/)
* сборка [Aspose.Words](../../../)


