---
title: ChartNumberFormat.FormatCode
second_title: Справочник по API Aspose.Words для .NET
description: ChartNumberFormat свойство. Получает или задает код формата применяемый к метке данных.
type: docs
weight: 10
url: /ru/net/aspose.words.drawing.charts/chartnumberformat/formatcode/
---
## ChartNumberFormat.FormatCode property

Получает или задает код формата, применяемый к метке данных.

```csharp
public string FormatCode { get; set; }
```

### Примечания

Числовое форматирование используется для изменения способа отображения значения в метке данных и может использоваться очень творчески. Примеры числовых форматов:

Номер - "#,##0.00"

Валюта - "\"$\"#,##0.00"

Время - "[$-x-systime]ч:мм:сс AM/PM"

Дата - "д/мм/гггг"

Процент - "0,00%"

Дробная часть - "# ?/?"

Научный - "0.00E+00"

Текст - "@"

Бухгалтерия - "_-\"$\"* #,##0.00_-;-\"$\"* #,##0.00_-;_-\"$\"* \"-\"??_ -;_-@_-"

Пользовательский с цветом - "[Красный]-#,##0.0"

### Примеры

Показывает, как задать форматирование значений диаграммы.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Column, 500, 300);
Chart chart = shape.Chart;

// Очистить серию демонстрационных данных диаграммы, чтобы начать с чистой диаграммы.
chart.Series.Clear();

// Добавляем на диаграмму пользовательский ряд с категориями по оси X,
 // и большие соответствующие числовые значения для оси Y.
chart.Series.Add("Aspose Test Series",
    new [] { "Word", "PDF", "Excel", "GoogleDocs", "Note" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });

 // Установите числовой формат меток деления оси Y, чтобы не группировать цифры запятыми.
chart.AxisY.NumberFormat.FormatCode = "#,##0";

// Этот флаг может переопределить указанное выше значение и вывести числовой формат из исходной ячейки.
Assert.False(chart.AxisY.NumberFormat.IsLinkedToSource);

doc.Save(ArtifactsDir + "Charts.SetNumberFormatToChartAxis.docx");
```

Показывает, как включить и настроить метки данных для серии диаграмм.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Добавьте линейный график, затем очистите ряд демонстрационных данных, чтобы начать с чистого графика,
// и затем установить заголовок.
Shape shape = builder.InsertChart(ChartType.Line, 500, 300);
Chart chart = shape.Chart;
chart.Series.Clear();
chart.Title.Text = "Monthly sales report";

// Вставьте пользовательскую серию диаграмм с месяцами в качестве категорий для оси X,
// и соответствующие десятичные числа для оси Y.
ChartSeries series = chart.Series.Add("Revenue", 
    new[] { "January", "February", "March" }, 
    new[] { 25.611d, 21.439d, 33.750d });

// Включите метки данных, а затем примените пользовательский числовой формат для значений, отображаемых в метках данных.
// Этот формат будет обрабатывать отображаемые десятичные значения как миллионы долларов США.
series.HasDataLabels = true;
ChartDataLabelCollection dataLabels = series.DataLabels;
dataLabels.ShowValue = true;
dataLabels.NumberFormat.FormatCode = "\"US$\" #,##0.000\"M\"";

doc.Save(ArtifactsDir + "Charts.DataLabelNumberFormat.docx");
```

### Смотрите также

* class [ChartNumberFormat](../)
* пространство имен [Aspose.Words.Drawing.Charts](../../chartnumberformat/)
* сборка [Aspose.Words](../../../)


