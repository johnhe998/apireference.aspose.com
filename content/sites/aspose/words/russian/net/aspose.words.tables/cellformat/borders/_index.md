---
title: CellFormat.Borders
second_title: Справочник по API Aspose.Words для .NET
description: CellFormat свойство. Получает набор границ ячейки.
type: docs
weight: 10
url: /ru/net/aspose.words.tables/cellformat/borders/
---
## CellFormat.Borders property

Получает набор границ ячейки.

```csharp
public BorderCollection Borders { get; }
```

### Примеры

Показывает, как объединить строки из двух таблиц в одну.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

// Ниже приведены два способа получения таблицы из документа.
// 1 - Из коллекции "Таблицы" узла Body:
Table firstTable = doc.FirstSection.Body.Tables[0];

// 2 - Используя метод "GetChild":
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);

// Добавляем все строки из текущей таблицы в следующую.
while (secondTable.HasChildNodes)
    firstTable.Rows.Add(secondTable.FirstRow);

// Удалить пустой контейнер таблицы.
secondTable.Remove();

doc.Save(ArtifactsDir + "Table.CombineTables.docx");
```

### Смотрите также

* class [BorderCollection](../../../aspose.words/bordercollection/)
* class [CellFormat](../)
* пространство имен [Aspose.Words.Tables](../../cellformat/)
* сборка [Aspose.Words](../../../)


