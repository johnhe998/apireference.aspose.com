---
title: Chart.SourceFullName
second_title: Справочник по API Aspose.Words для .NET
description: Chart свойство. Получает путь и имя файла xls/xlsx с которым связана эта диаграмма.
type: docs
weight: 60
url: /ru/net/aspose.words.drawing.charts/chart/sourcefullname/
---
## Chart.SourceFullName property

Получает путь и имя файла xls/xlsx, с которым связана эта диаграмма.

```csharp
public string SourceFullName { get; set; }
```

### Примеры

Показывает, как получить полное имя внешнего документа xls/xlsx, если диаграмма связана.

```csharp
Document doc = new Document(MyDir + "Shape with linked chart.docx");

Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);

Assert.True(shape.Chart.SourceFullName.Contains("Examples\\Data\\Spreadsheet.xlsx"));
```

### Смотрите также

* class [Chart](../)
* пространство имен [Aspose.Words.Drawing.Charts](../../chart/)
* сборка [Aspose.Words](../../../)


