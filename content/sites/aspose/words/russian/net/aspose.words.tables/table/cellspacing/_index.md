---
title: Table.CellSpacing
second_title: Справочник по API Aspose.Words для .NET
description: Table свойство. Получает или задает расстояние в пунктах между ячейками.
type: docs
weight: 100
url: /ru/net/aspose.words.tables/table/cellspacing/
---
## Table.CellSpacing property

Получает или задает расстояние (в пунктах) между ячейками.

```csharp
public double CellSpacing { get; set; }
```

### Примеры

Показывает, как включить интервалы между отдельными ячейками в таблице.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Animal");
builder.InsertCell();
builder.Write("Class");
builder.EndRow();
builder.InsertCell();
builder.Write("Dog");
builder.InsertCell();
builder.Write("Mammal");
builder.EndTable();

table.CellSpacing = 3;

// Установите для свойства "AllowCellSpacing" значение "true", чтобы разрешить интервалы между ячейками
// с величиной, равной значению свойства "CellSpacing" в пунктах.
// Установите для свойства «AllowCellSpacing» значение «false», чтобы отключить интервал между ячейками
// и игнорируем значение свойства "CellSpacing".
table.AllowCellSpacing = allowCellSpacing;

doc.Save(ArtifactsDir + "Table.AllowCellSpacing.html");

// Настройка свойства «CellSpacing» автоматически активирует интервал между ячейками.
table.CellSpacing = 5;

Assert.True(table.AllowCellSpacing);
```

Показывает, как создавать пользовательские настройки стиля для таблицы.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Name");
builder.InsertCell();
builder.Write("مرحبًا");
builder.EndRow();
builder.InsertCell();
builder.InsertCell();
builder.EndTable();

TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.AllowBreakAcrossPages = true;
tableStyle.Bidi = true;
tableStyle.CellSpacing = 5;
tableStyle.BottomPadding = 20;
tableStyle.LeftPadding = 5;
tableStyle.RightPadding = 10;
tableStyle.TopPadding = 20;
tableStyle.Shading.BackgroundPatternColor = Color.AntiqueWhite;
tableStyle.Borders.Color = Color.Blue;
tableStyle.Borders.LineStyle = LineStyle.DotDash;
tableStyle.VerticalAlignment = CellVerticalAlignment.Center;

table.Style = tableStyle;

// Установка свойств стиля таблицы может повлиять на свойства самой таблицы.
Assert.True(table.Bidi);
Assert.AreEqual(5.0d, table.CellSpacing);
Assert.AreEqual("MyTableStyle1", table.StyleName);

doc.Save(ArtifactsDir + "Table.TableStyleCreation.docx");
```

### Смотрите также

* class [Table](../)
* пространство имен [Aspose.Words.Tables](../../table/)
* сборка [Aspose.Words](../../../)


