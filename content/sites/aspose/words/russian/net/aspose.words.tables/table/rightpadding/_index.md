---
title: Table.RightPadding
second_title: Справочник по API Aspose.Words для .NET
description: Table свойство. Получает или задает количество места в пунктах для добавления справа от содержимого ячеек.
type: docs
weight: 250
url: /ru/net/aspose.words.tables/table/rightpadding/
---
## Table.RightPadding property

Получает или задает количество места (в пунктах) для добавления справа от содержимого ячеек.

```csharp
public double RightPadding { get; set; }
```

### Примеры

Показывает, как настроить заполнение содержимого в таблице.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Row 1, cell 1.");
builder.InsertCell();
builder.Write("Row 1, cell 2.");
builder.EndTable();

// Для каждой ячейки в таблице устанавливаем расстояние между ее содержимым и каждой из ее границ. 
// Эта таблица будет поддерживать минимальное расстояние отступа за счет переноса текста.
table.LeftPadding = 30;
table.RightPadding = 60;
table.TopPadding = 10;
table.BottomPadding = 90;
table.PreferredWidth = PreferredWidth.FromPoints(250);

doc.Save(ArtifactsDir + "DocumentBuilder.SetRowFormatting.docx");
```

### Смотрите также

* class [Table](../)
* пространство имен [Aspose.Words.Tables](../../table/)
* сборка [Aspose.Words](../../../)


