---
title: Row.Row
second_title: Справочник по API Aspose.Words для .NET
description: Row строитель. Инициализирует новый экземпляр Строка класс.
type: docs
weight: 10
url: /ru/net/aspose.words.tables/row/row/
---
## Row constructor

Инициализирует новый экземпляр **Строка** класс.

```csharp
public Row(DocumentBase doc)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| doc | DocumentBase | Документ владельца. |

### Примечания

Когда **Строка** создан, он принадлежит указанному документу, но не является частью документа и **Родительский узел** нулевой.

Чтобы добавить **Строка**к документу используйте InsertAfter или InsertBefore для таблицы, в которую вы хотите вставить строку.

### Примеры

Показывает, как построить вложенную таблицу без использования построителя документов.

```csharp
public void CreateNestedTable()
{
    Document doc = new Document();

    // Создадим внешнюю таблицу с тремя строками и четырьмя столбцами, а затем добавим ее в документ.
    Table outerTable = CreateTable(doc, 3, 4, "Outer Table");
    doc.FirstSection.Body.AppendChild(outerTable);

    // Создайте еще одну таблицу с двумя строками и двумя столбцами, а затем вставьте ее в первую ячейку первой таблицы.
    Table innerTable = CreateTable(doc, 2, 2, "Inner Table");
    outerTable.FirstRow.FirstCell.AppendChild(innerTable);

    doc.Save(ArtifactsDir + "Table.CreateNestedTable.docx");
}

/// <summary>
/// Создает новую таблицу в документе с заданными размерами и текстом в каждой ячейке.
/// </summary>
private static Table CreateTable(Document doc, int rowCount, int cellCount, string cellText)
{
    Table table = new Table(doc);

    for (int rowId = 1; rowId <= rowCount; rowId++)
    {
        Row row = new Row(doc);
        table.AppendChild(row);

        for (int cellId = 1; cellId <= cellCount; cellId++)
        {
            Cell cell = new Cell(doc);
            cell.AppendChild(new Paragraph(doc));
            cell.FirstParagraph.AppendChild(new Run(doc, cellText));

            row.AppendChild(cell);
        }
    }

    // Вы можете использовать свойства «Заголовок» и «Описание», чтобы добавить заголовок и описание соответственно к вашей таблице.
    // В таблице должна быть хотя бы одна строка, прежде чем мы сможем использовать эти свойства.
    // Эти свойства имеют значение для документов .docx, совместимых с ISO/IEC 29500 (см. класс OoxmlCompliance).
    // Если мы сохраняем документ в форматах, предшествующих ISO/IEC 29500, Microsoft Word игнорирует эти свойства.
    table.Title = "Aspose table title";
    table.Description = "Aspose table description";

    return table;
}
```

### Смотрите также

* class [DocumentBase](../../../aspose.words/documentbase/)
* class [Row](../)
* пространство имен [Aspose.Words.Tables](../../row/)
* сборка [Aspose.Words](../../../)


