---
title: RowCollection.ToArray
second_title: Справочник по API Aspose.Words для .NET
description: RowCollection метод. Копирует все строки из коллекции в новый массив строк.
type: docs
weight: 20
url: /ru/net/aspose.words.tables/rowcollection/toarray/
---
## RowCollection.ToArray method

Копирует все строки из коллекции в новый массив строк.

```csharp
public Row[] ToArray()
```

### Возвращаемое значение

Массив строк.

### Примеры

Показывает, как выполнить итерацию по всем таблицам в документе и распечатать содержимое каждой ячейки.

```csharp
Document doc = new Document(MyDir + "Tables.docx");
TableCollection tables = doc.FirstSection.Body.Tables;

Assert.AreEqual(2, tables.ToArray().Length);

for (int i = 0; i < tables.Count; i++)
{
    Console.WriteLine($"Start of Table {i}");

    RowCollection rows = tables[i].Rows;

    // Мы можем использовать метод "ToArray" для набора строк, чтобы клонировать его в массив.
    Assert.AreEqual(rows, rows.ToArray());
    Assert.AreNotSame(rows, rows.ToArray());

    for (int j = 0; j < rows.Count; j++)
    {
        Console.WriteLine($"\tStart of Row {j}");

        CellCollection cells = rows[j].Cells;

        // Мы можем использовать метод "ToArray" для набора ячеек, чтобы клонировать его в массив.
        Assert.AreEqual(cells, cells.ToArray());
        Assert.AreNotSame(cells, cells.ToArray());

        for (int k = 0; k < cells.Count; k++)
        {
            string cellText = cells[k].ToString(SaveFormat.Text).Trim();
            Console.WriteLine($"\t\tContents of Cell:{k} = \"{cellText}\"");
        }

        Console.WriteLine($"\tEnd of Row {j}");
    }

    Console.WriteLine($"End of Table {i}\n");
}
```

### Смотрите также

* class [Row](../../row/)
* class [RowCollection](../)
* пространство имен [Aspose.Words.Tables](../../rowcollection/)
* сборка [Aspose.Words](../../../)


