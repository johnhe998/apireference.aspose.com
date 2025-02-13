---
title: ChartSeriesCollection.Count
second_title: Справочник по API Aspose.Words для .NET
description: ChartSeriesCollection свойство. Возвращает количествоChartSeries в этой коллекции.
type: docs
weight: 10
url: /ru/net/aspose.words.drawing.charts/chartseriescollection/count/
---
## ChartSeriesCollection.Count property

Возвращает количество[`ChartSeries`](../../chartseries/) в этой коллекции.

```csharp
public int Count { get; }
```

### Примеры

Показывает, как добавлять и удалять ряды данных на диаграмме.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Вставьте столбчатую диаграмму, которая по умолчанию будет содержать три ряда демонстрационных данных.
Shape chartShape = builder.InsertChart(ChartType.Column, 400, 300);
Chart chart = chartShape.Chart;

// Каждая серия имеет четыре десятичных значения: по одному для каждой из четырех категорий.
// Четыре кластера из трех столбцов будут представлять эти данные.
ChartSeriesCollection chartData = chart.Series;

Assert.AreEqual(3, chartData.Count);

// Вывести название каждой серии на диаграмме.
using (IEnumerator<ChartSeries> enumerator = chart.Series.GetEnumerator())
{
    while (enumerator.MoveNext())
    {
        Console.WriteLine(enumerator.Current.Name);
    }
}

// Это названия категорий на графике.
string[] categories = { "Category 1", "Category 2", "Category 3", "Category 4" };

// Мы можем добавить серию с новыми значениями для существующих категорий.
// Эта диаграмма теперь будет содержать четыре кластера по четыре столбца.
chart.Series.Add("Series 4", categories, new[] { 4.4, 7.0, 3.5, 2.1 });

// Серия диаграмм также может быть удалена по индексу, как здесь.
// Это удалит одну из трех демонстрационных серий, поставляемых с диаграммой.
chartData.RemoveAt(2);

Assert.False(chartData.Any(s => s.Name == "Series 3"));

// С помощью этого метода мы также можем очистить все данные графика сразу.
// При создании нового графика это способ стереть все демонстрационные данные
// прежде чем мы сможем начать работу с пустой диаграммой.
chartData.Clear();
```

### Смотрите также

* class [ChartSeriesCollection](../)
* пространство имен [Aspose.Words.Drawing.Charts](../../chartseriescollection/)
* сборка [Aspose.Words](../../../)


