---
title: Row.RowFormat
second_title: Справочник по API Aspose.Words для .NET
description: Row свойство. Предоставляет доступ к свойствам форматирования строки.
type: docs
weight: 90
url: /ru/net/aspose.words.tables/row/rowformat/
---
## Row.RowFormat property

Предоставляет доступ к свойствам форматирования строки.

```csharp
public RowFormat RowFormat { get; }
```

### Примеры

Показывает, как изменить форматирование строки таблицы.

```csharp
Document doc = new Document(MyDir + "Tables.docx");
Table table = doc.FirstSection.Body.Tables[0];

// Используйте свойство «RowFormat» первой строки, чтобы установить форматирование, которое изменяет внешний вид всей строки.
Row firstRow = table.FirstRow;
firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
firstRow.RowFormat.HeightRule = HeightRule.Auto;
firstRow.RowFormat.AllowBreakAcrossPages = true;

doc.Save(ArtifactsDir + "Table.RowFormat.docx");
```

Показывает, как изменить формат строк и ячеек в таблице.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("City");
builder.InsertCell();
builder.Write("Country");
builder.EndRow();
builder.InsertCell();
builder.Write("London");
builder.InsertCell();
builder.Write("U.K.");
builder.EndTable();

// Используйте свойство "RowFormat" первой строки, чтобы изменить форматирование
// содержимого всех ячеек в этой строке.
RowFormat rowFormat = table.FirstRow.RowFormat;
rowFormat.Height = 25;
rowFormat.Borders[BorderType.Bottom].Color = Color.Red;

// Используйте свойство «CellFormat» первой ячейки в последней строке, чтобы изменить форматирование содержимого этой ячейки.
CellFormat cellFormat = table.LastRow.FirstCell.CellFormat;
cellFormat.Width = 100;
cellFormat.Shading.BackgroundPatternColor = Color.Orange;

doc.Save(ArtifactsDir + "Table.RowCellFormat.docx");
```

### Смотрите также

* class [RowFormat](../../rowformat/)
* class [Row](../)
* пространство имен [Aspose.Words.Tables](../../row/)
* сборка [Aspose.Words](../../../)


