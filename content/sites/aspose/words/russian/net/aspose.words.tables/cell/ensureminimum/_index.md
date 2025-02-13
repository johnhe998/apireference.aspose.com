---
title: Cell.EnsureMinimum
second_title: Справочник по API Aspose.Words для .NET
description: Cell метод. Если последний дочерний элемент не является абзацем создает и добавляет один пустой абзац.
type: docs
weight: 120
url: /ru/net/aspose.words.tables/cell/ensureminimum/
---
## Cell.EnsureMinimum method

Если последний дочерний элемент не является абзацем, создает и добавляет один пустой абзац.

```csharp
public void EnsureMinimum()
```

### Примеры

Показывает, как убедиться, что узел ячейки содержит узлы, необходимые для добавления в него содержимого.

```csharp
Document doc = new Document();
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
Row row = new Row(doc);
table.AppendChild(row);
Cell cell = new Cell(doc);
row.AppendChild(cell);

// Ячейки могут содержать абзацы с типичными элементами, такими как прогоны, фигуры и даже другие таблицы.
// В нашей новой ячейке нет абзацев, и мы не можем добавлять в нее содержимое, такое как узлы запуска и формы, пока они не будут созданы.
Assert.AreEqual(0, cell.GetChildNodes(NodeType.Any, true).Count);

// Вызов метода "EnsureMinimum" для ячейки гарантирует, что
// в ячейке есть хотя бы один пустой абзац, в который мы можем затем добавить содержимое.
cell.EnsureMinimum();
cell.FirstParagraph.AppendChild(new Run(doc, "Hello world!"));
```

### Смотрите также

* class [Cell](../)
* пространство имен [Aspose.Words.Tables](../../cell/)
* сборка [Aspose.Words](../../../)


