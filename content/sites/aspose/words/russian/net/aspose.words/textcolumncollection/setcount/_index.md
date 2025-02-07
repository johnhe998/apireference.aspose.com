---
title: TextColumnCollection.SetCount
second_title: Справочник по API Aspose.Words для .NET
description: TextColumnCollection метод. Располагает текст в указанное количество текстовых столбцов.
type: docs
weight: 70
url: /ru/net/aspose.words/textcolumncollection/setcount/
---
## TextColumnCollection.SetCount method

Располагает текст в указанное количество текстовых столбцов.

```csharp
public void SetCount(int newCount)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| newCount | Int32 | Количество колонок, в которые должен быть помещен текст. |

### Примечания

Когда[`EvenlySpaced`](../evenlyspaced/) является **ЛОЖЬ** а вы увеличиваете количество столбцов, new[`TextColumn`](../../textcolumn/) объекты создаются с нулевой шириной и интервалом. Вам необходимо установить ширину и интервал для новых столбцов.

### Примеры

Показывает, как создать несколько равномерно расположенных столбцов в разделе.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

TextColumnCollection columns = builder.PageSetup.TextColumns;
columns.Spacing = 100;
columns.SetCount(2);

builder.Writeln("Column 1.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Writeln("Column 2.");

doc.Save(ArtifactsDir + "PageSetup.ColumnsSameWidth.docx");
```

### Смотрите также

* class [TextColumnCollection](../)
* пространство имен [Aspose.Words](../../textcolumncollection/)
* сборка [Aspose.Words](../../../)


