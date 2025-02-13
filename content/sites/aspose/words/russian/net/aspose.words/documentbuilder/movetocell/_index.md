---
title: DocumentBuilder.MoveToCell
second_title: Справочник по API Aspose.Words для .NET
description: DocumentBuilder метод. Перемещает курсор в ячейку таблицы в текущем разделе.
type: docs
weight: 480
url: /ru/net/aspose.words/documentbuilder/movetocell/
---
## DocumentBuilder.MoveToCell method

Перемещает курсор в ячейку таблицы в текущем разделе.

```csharp
public void MoveToCell(int tableIndex, int rowIndex, int columnIndex, int characterIndex)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| tableIndex | Int32 | Индекс таблицы для перехода. |
| rowIndex | Int32 | Индекс строки в таблице. |
| columnIndex | Int32 | Индекс столбца в таблице. |
| characterIndex | Int32 | Индекс символа внутри ячейки. Отрицательное значение позволяет указать позицию от конца ячейки. Используйте -1, чтобы перейти в конец ячейки. |

### Примечания

Навигация осуществляется внутри текущей истории текущего раздела.

Для параметров индекса, когда индекс больше или равен 0, он указывает индекс from , начиная с 0, являющегося первым элементом. Когда индекс меньше 0, он указывает индекс from , конец которого -1 является последним элементом.

### Примеры

Показывает, как переместить курсор конструктора документов в ячейку таблицы.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Создаем пустую таблицу 2x2.
builder.StartTable();
builder.InsertCell();
builder.InsertCell();
builder.EndRow();
builder.InsertCell();
builder.InsertCell();
builder.EndTable();

// Так как мы завершили таблицу методом EndTable,
// курсор конструктора документов в данный момент находится за пределами таблицы.
// Этот курсор имеет ту же функцию, что и мигающий текстовый курсор Microsoft Word.
// Его также можно переместить в другое место в документе с помощью методов компоновщика MoveTo.
// Мы можем переместить курсор обратно внутри таблицы в определенную ячейку.
builder.MoveToCell(0, 1, 1, 0);
builder.Write("Column 2, cell 2.");

doc.Save(ArtifactsDir + "DocumentBuilder.MoveToCell.docx");
```

### Смотрите также

* class [DocumentBuilder](../)
* пространство имен [Aspose.Words](../../documentbuilder/)
* сборка [Aspose.Words](../../../)


