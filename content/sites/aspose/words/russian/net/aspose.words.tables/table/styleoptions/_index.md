---
title: Table.StyleOptions
second_title: Справочник по API Aspose.Words для .NET
description: Table свойство. Получает или задает битовые флаги указывающие как стиль таблицы применяется к этой таблице.
type: docs
weight: 300
url: /ru/net/aspose.words.tables/table/styleoptions/
---
## Table.StyleOptions property

Получает или задает битовые флаги, указывающие, как стиль таблицы применяется к этой таблице.

```csharp
public TableStyleOptions StyleOptions { get; set; }
```

### Примеры

Показывает, как создать новую таблицу при применении стиля.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();

// Мы должны вставить хотя бы одну строку, прежде чем задавать какое-либо форматирование таблицы.
builder.InsertCell();

// Установить используемый стиль таблицы на основе идентификатора стиля.
// Обратите внимание, что не все стили таблиц доступны при сохранении в формате .doc.
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;

// Частично применяем стиль к функциям таблицы на основе предикатов, затем строим таблицу.
table.StyleOptions =
    TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
table.AutoFit(AutoFitBehavior.AutoFitToContents);

builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder.InsertCell();
builder.Writeln("Quantity (kg)");
builder.EndRow();

builder.InsertCell();
builder.Writeln("Apples");
builder.InsertCell();
builder.Writeln("20");
builder.EndRow();

builder.InsertCell();
builder.Writeln("Bananas");
builder.InsertCell();
builder.Writeln("40");
builder.EndRow();

builder.InsertCell();
builder.Writeln("Carrots");
builder.InsertCell();
builder.Writeln("50");
builder.EndRow();

doc.Save(ArtifactsDir + "DocumentBuilder.InsertTableWithStyle.docx");
```

### Смотрите также

* enum [TableStyleOptions](../../tablestyleoptions/)
* class [Table](../)
* пространство имен [Aspose.Words.Tables](../../table/)
* сборка [Aspose.Words](../../../)


