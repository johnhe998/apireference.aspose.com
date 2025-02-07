---
title: DocumentBuilder.DeleteRow
second_title: Справочник по API Aspose.Words для .NET
description: DocumentBuilder метод. Удаляет строку из таблицы.
type: docs
weight: 180
url: /ru/net/aspose.words/documentbuilder/deleterow/
---
## DocumentBuilder.DeleteRow method

Удаляет строку из таблицы.

```csharp
public Row DeleteRow(int tableIndex, int rowIndex)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| tableIndex | Int32 | Индекс таблицы. |
| rowIndex | Int32 | Индекс строки в таблице. |

### Возвращаемое значение

Узел строки, который был только что удален.

### Примечания

Если курсор находится внутри удаляемой строки, курсор перемещается на следующую строку или на следующий абзац после таблицы.

Если вы удаляете строку из таблицы, которая содержит только одну строку, удаляется таблица whole .

Для параметров индекса, когда индекс больше или равен 0, он указывает индекс from , начиная с 0, являющегося первым элементом. Когда индекс меньше 0, он указывает индекс from , конец которого -1 является последним элементом.

### Примеры

Показывает, как удалить строку из таблицы.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Row 1, cell 1.");
builder.InsertCell();
builder.Write("Row 1, cell 2.");
builder.EndRow();
builder.InsertCell();
builder.Write("Row 2, cell 1.");
builder.InsertCell();
builder.Write("Row 2, cell 2.");
builder.EndTable();

Assert.AreEqual(2, table.Rows.Count);

// Удалить первую строку первой таблицы в документе.
builder.DeleteRow(0, 0);

Assert.AreEqual(1, table.Rows.Count);
Assert.AreEqual("Row 2, cell 1.\aRow 2, cell 2.\a\a", table.GetText().Trim());
```

### Смотрите также

* class [Row](../../../aspose.words.tables/row/)
* class [DocumentBuilder](../)
* пространство имен [Aspose.Words](../../documentbuilder/)
* сборка [Aspose.Words](../../../)


