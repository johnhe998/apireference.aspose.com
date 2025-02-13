---
title: DocumentBuilder.EndColumnBookmark
second_title: Справочник по API Aspose.Words для .NET
description: DocumentBuilder метод. Помечает текущую позицию в документе как конец закладки столбца. Позиция должна быть в ячейке таблицы.
type: docs
weight: 200
url: /ru/net/aspose.words/documentbuilder/endcolumnbookmark/
---
## DocumentBuilder.EndColumnBookmark method

Помечает текущую позицию в документе как конец закладки столбца. Позиция должна быть в ячейке таблицы.

```csharp
public BookmarkEnd EndColumnBookmark(string bookmarkName)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| bookmarkName | String | Название закладки. |

### Возвращаемое значение

Только что созданный конечный узел закладки.

### Примечания

Закладка столбца охватывает один или несколько столбцов в диапазоне строк. Чтобы создать действительную закладку, you нужно вызвать оба[`StartColumnBookmark`](../startcolumnbookmark/) а также`EndColumnBookmark` с тем же  **bookmarkName** параметр.

Неправильно сформированные закладки или закладки с повторяющимися именами будут игнорироваться при сохранении документа.

Фактическое положение вставленного[`BookmarkEnd`](../../bookmarkend/) node может отличаться от текущей позиции построителя document .

### Примеры

Показывает, как создать закладку столбца.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartTable();

builder.InsertCell();
// Ячейки 1,2,4,5 будут добавлены в закладки.
builder.StartColumnBookmark("MyBookmark_1");
// Неправильно сформированные закладки или закладки с повторяющимися именами будут игнорироваться при сохранении документа.
builder.StartColumnBookmark("MyBookmark_1");
builder.StartColumnBookmark("BadStartBookmark");
builder.Write("Cell 1");

builder.InsertCell();
builder.Write("Cell 2");

builder.InsertCell();
builder.Write("Cell 3");

builder.EndRow();

builder.InsertCell();
builder.Write("Cell 4");

builder.InsertCell();
builder.Write("Cell 5");
builder.EndColumnBookmark("MyBookmark_1");
builder.EndColumnBookmark("MyBookmark_1");

builder.InsertCell();
builder.Write("Cell 6");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "Bookmarks.CreateColumnBookmark.docx");
```

### Смотрите также

* class [BookmarkEnd](../../bookmarkend/)
* class [DocumentBuilder](../)
* пространство имен [Aspose.Words](../../documentbuilder/)
* сборка [Aspose.Words](../../../)


