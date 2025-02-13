---
title: ChartSeriesCollection.Add
second_title: Aspose.Words für .NET-API-Referenz
description: ChartSeriesCollection methode. Fügt neu hinzuChartSerieszu dieser Sammlung hinzufügen. Verwenden Sie diese Methode um Serien zu jeder Art von Balken Säulen Linien und Oberflächendiagrammen hinzuzufügen.
type: docs
weight: 30
url: /de/net/aspose.words.drawing.charts/chartseriescollection/add/
---
## Add(string, string[], double[]) {#add_3}

Fügt neu hinzu[`ChartSeries`](../../chartseries/)zu dieser Sammlung hinzufügen. Verwenden Sie diese Methode, um Serien zu jeder Art von Balken-, Säulen-, Linien- und Oberflächendiagrammen hinzuzufügen.

```csharp
public ChartSeries Add(string seriesName, string[] categories, double[] values)
```

### Rückgabewert

Kürzlich hinzugefügt[`ChartSeries`](../../chartseries/) Objekt.

### Beispiele

Zeigt, wie ein geeigneter Typ von Diagrammreihen für einen Diagrammtyp erstellt wird.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Es gibt mehrere Möglichkeiten, die Seriensammlung eines Diagramms zu füllen.
    // Unterschiedliche Reihenschemata sind für unterschiedliche Diagrammtypen vorgesehen.
    // 1 - Säulendiagramm mit gruppierten und gebänderten Säulen entlang der X-Achse nach Kategorie:
    Chart chart = AppendChart(builder, ChartType.Column, 500, 300);

    string[] categories = { "Category 1", "Category 2", "Category 3" };

    // Fügen Sie zwei Reihen von Dezimalwerten ein, die einen Wert für jede entsprechende Kategorie enthalten.
    // Dieses Säulendiagramm hat drei Gruppen mit jeweils zwei Säulen.
    chart.Series.Add("Series 1", categories, new [] { 76.6, 82.1, 91.6 });
    chart.Series.Add("Series 2", categories, new [] { 64.2, 79.5, 94.0 });

    // Kategorien werden entlang der X-Achse verteilt und Werte werden entlang der Y-Achse verteilt.
    Assert.AreEqual(ChartAxisType.Category, chart.AxisX.Type);
    Assert.AreEqual(ChartAxisType.Value, chart.AxisY.Type);

    // 2 - Flächendiagramm mit Datumsangaben entlang der X-Achse:
    chart = AppendChart(builder, ChartType.Area, 500, 300);

    DateTime[] dates = { new DateTime(2014, 3, 31),
        new DateTime(2017, 1, 23),
        new DateTime(2017, 6, 18),
        new DateTime(2019, 11, 22),
        new DateTime(2020, 9, 7)
    };

    // Eine Reihe mit einem Dezimalwert für jedes jeweilige Datum einfügen.
    // Die Daten werden entlang einer linearen X-Achse verteilt,
    // und die dieser Reihe hinzugefügten Werte erzeugen Datenpunkte.
    chart.Series.Add("Series 1", dates, new [] { 15.8, 21.5, 22.9, 28.7, 33.1 });

    Assert.AreEqual(ChartAxisType.Category, chart.AxisX.Type);
    Assert.AreEqual(ChartAxisType.Value, chart.AxisY.Type);

    // 3 - 2D-Streudiagramm:
    chart = AppendChart(builder, ChartType.Scatter, 500, 300);

    // Jede Reihe benötigt zwei Dezimalarrays gleicher Länge.
    // Das erste Array enthält X-Werte und das zweite enthält entsprechende Y-Werte
    // von Datenpunkten auf dem Diagramm des Diagramms.
    chart.Series.Add("Series 1", 
        new[] { 3.1, 3.5, 6.3, 4.1, 2.2, 8.3, 1.2, 3.6 }, 
        new[] { 3.1, 6.3, 4.6, 0.9, 8.5, 4.2, 2.3, 9.9 });
    chart.Series.Add("Series 2", 
        new[] { 2.6, 7.3, 4.5, 6.6, 2.1, 9.3, 0.7, 3.3 }, 
        new[] { 7.1, 6.6, 3.5, 7.8, 7.7, 9.5, 1.3, 4.6 });

    Assert.AreEqual(ChartAxisType.Value, chart.AxisX.Type);
    Assert.AreEqual(ChartAxisType.Value, chart.AxisY.Type);

    // 4 - Blasendiagramm:
    chart = AppendChart(builder, ChartType.Bubble, 500, 300);

    // Jede Reihe benötigt drei Dezimalarrays gleicher Länge.
    // Das erste Array enthält X-Werte, das zweite enthält entsprechende Y-Werte,
    // und der dritte enthält Durchmesser für jeden der Datenpunkte des Diagramms.
    chart.Series.Add("Series 1", 
        new [] { 1.1, 5.0, 9.8 }, 
        new [] { 1.2, 4.9, 9.9 }, 
        new [] { 2.0, 4.0, 8.0 });

    doc.Save(ArtifactsDir + "Charts.ChartSeriesCollection.docx");
}

/// <summary>
/// Fügen Sie ein Diagramm mit einem Document Builder mit einem bestimmten ChartType, Breite und Höhe ein und entfernen Sie seine Demodaten.
/// </summary>
private static Chart AppendChart(DocumentBuilder builder, ChartType chartType, double width, double height)
{
    Shape chartShape = builder.InsertChart(chartType, width, height);
    Chart chart = chartShape.Chart;
    chart.Series.Clear();
    return chart;
}
```

### Siehe auch

* class [ChartSeries](../../chartseries/)
* class [ChartSeriesCollection](../)
* namensraum [Aspose.Words.Drawing.Charts](../../chartseriescollection/)
* Montage [Aspose.Words](../../../)

---

## Add(string, double[], double[]) {#add}

Fügt neu hinzu[`ChartSeries`](../../chartseries/) zu dieser Sammlung hinzufügen. Verwenden Sie diese Methode, um Serien zu jeder Art von Streudiagrammen hinzuzufügen.

```csharp
public ChartSeries Add(string seriesName, double[] xValues, double[] yValues)
```

### Rückgabewert

Kürzlich hinzugefügt[`ChartSeries`](../../chartseries/) Objekt.

### Beispiele

Zeigt, wie ein geeigneter Typ von Diagrammreihen für einen Diagrammtyp erstellt wird.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Es gibt mehrere Möglichkeiten, die Seriensammlung eines Diagramms zu füllen.
    // Unterschiedliche Reihenschemata sind für unterschiedliche Diagrammtypen vorgesehen.
    // 1 - Säulendiagramm mit gruppierten und gebänderten Säulen entlang der X-Achse nach Kategorie:
    Chart chart = AppendChart(builder, ChartType.Column, 500, 300);

    string[] categories = { "Category 1", "Category 2", "Category 3" };

    // Fügen Sie zwei Reihen von Dezimalwerten ein, die einen Wert für jede entsprechende Kategorie enthalten.
    // Dieses Säulendiagramm hat drei Gruppen mit jeweils zwei Säulen.
    chart.Series.Add("Series 1", categories, new [] { 76.6, 82.1, 91.6 });
    chart.Series.Add("Series 2", categories, new [] { 64.2, 79.5, 94.0 });

    // Kategorien werden entlang der X-Achse verteilt und Werte werden entlang der Y-Achse verteilt.
    Assert.AreEqual(ChartAxisType.Category, chart.AxisX.Type);
    Assert.AreEqual(ChartAxisType.Value, chart.AxisY.Type);

    // 2 - Flächendiagramm mit Datumsangaben entlang der X-Achse:
    chart = AppendChart(builder, ChartType.Area, 500, 300);

    DateTime[] dates = { new DateTime(2014, 3, 31),
        new DateTime(2017, 1, 23),
        new DateTime(2017, 6, 18),
        new DateTime(2019, 11, 22),
        new DateTime(2020, 9, 7)
    };

    // Eine Reihe mit einem Dezimalwert für jedes jeweilige Datum einfügen.
    // Die Daten werden entlang einer linearen X-Achse verteilt,
    // und die dieser Reihe hinzugefügten Werte erzeugen Datenpunkte.
    chart.Series.Add("Series 1", dates, new [] { 15.8, 21.5, 22.9, 28.7, 33.1 });

    Assert.AreEqual(ChartAxisType.Category, chart.AxisX.Type);
    Assert.AreEqual(ChartAxisType.Value, chart.AxisY.Type);

    // 3 - 2D-Streudiagramm:
    chart = AppendChart(builder, ChartType.Scatter, 500, 300);

    // Jede Reihe benötigt zwei Dezimalarrays gleicher Länge.
    // Das erste Array enthält X-Werte und das zweite enthält entsprechende Y-Werte
    // von Datenpunkten auf dem Diagramm des Diagramms.
    chart.Series.Add("Series 1", 
        new[] { 3.1, 3.5, 6.3, 4.1, 2.2, 8.3, 1.2, 3.6 }, 
        new[] { 3.1, 6.3, 4.6, 0.9, 8.5, 4.2, 2.3, 9.9 });
    chart.Series.Add("Series 2", 
        new[] { 2.6, 7.3, 4.5, 6.6, 2.1, 9.3, 0.7, 3.3 }, 
        new[] { 7.1, 6.6, 3.5, 7.8, 7.7, 9.5, 1.3, 4.6 });

    Assert.AreEqual(ChartAxisType.Value, chart.AxisX.Type);
    Assert.AreEqual(ChartAxisType.Value, chart.AxisY.Type);

    // 4 - Blasendiagramm:
    chart = AppendChart(builder, ChartType.Bubble, 500, 300);

    // Jede Reihe benötigt drei Dezimalarrays gleicher Länge.
    // Das erste Array enthält X-Werte, das zweite enthält entsprechende Y-Werte,
    // und der dritte enthält Durchmesser für jeden der Datenpunkte des Diagramms.
    chart.Series.Add("Series 1", 
        new [] { 1.1, 5.0, 9.8 }, 
        new [] { 1.2, 4.9, 9.9 }, 
        new [] { 2.0, 4.0, 8.0 });

    doc.Save(ArtifactsDir + "Charts.ChartSeriesCollection.docx");
}

/// <summary>
/// Fügen Sie ein Diagramm mit einem Document Builder mit einem bestimmten ChartType, Breite und Höhe ein und entfernen Sie seine Demodaten.
/// </summary>
private static Chart AppendChart(DocumentBuilder builder, ChartType chartType, double width, double height)
{
    Shape chartShape = builder.InsertChart(chartType, width, height);
    Chart chart = chartShape.Chart;
    chart.Series.Clear();
    return chart;
}
```

### Siehe auch

* class [ChartSeries](../../chartseries/)
* class [ChartSeriesCollection](../)
* namensraum [Aspose.Words.Drawing.Charts](../../chartseriescollection/)
* Montage [Aspose.Words](../../../)

---

## Add(string, DateTime[], double[]) {#add_2}

Fügt neu hinzu[`ChartSeries`](../../chartseries/) zu dieser Sammlung. Verwenden Sie diese Methode, um Serien zu jeder Art von Flächen-, Radar- und Aktiendiagrammen hinzuzufügen.

```csharp
public ChartSeries Add(string seriesName, DateTime[] dates, double[] values)
```

### Beispiele

Zeigt, wie ein geeigneter Typ von Diagrammreihen für einen Diagrammtyp erstellt wird.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Es gibt mehrere Möglichkeiten, die Seriensammlung eines Diagramms zu füllen.
    // Unterschiedliche Reihenschemata sind für unterschiedliche Diagrammtypen vorgesehen.
    // 1 - Säulendiagramm mit gruppierten und gebänderten Säulen entlang der X-Achse nach Kategorie:
    Chart chart = AppendChart(builder, ChartType.Column, 500, 300);

    string[] categories = { "Category 1", "Category 2", "Category 3" };

    // Fügen Sie zwei Reihen von Dezimalwerten ein, die einen Wert für jede entsprechende Kategorie enthalten.
    // Dieses Säulendiagramm hat drei Gruppen mit jeweils zwei Säulen.
    chart.Series.Add("Series 1", categories, new [] { 76.6, 82.1, 91.6 });
    chart.Series.Add("Series 2", categories, new [] { 64.2, 79.5, 94.0 });

    // Kategorien werden entlang der X-Achse verteilt und Werte werden entlang der Y-Achse verteilt.
    Assert.AreEqual(ChartAxisType.Category, chart.AxisX.Type);
    Assert.AreEqual(ChartAxisType.Value, chart.AxisY.Type);

    // 2 - Flächendiagramm mit Datumsangaben entlang der X-Achse:
    chart = AppendChart(builder, ChartType.Area, 500, 300);

    DateTime[] dates = { new DateTime(2014, 3, 31),
        new DateTime(2017, 1, 23),
        new DateTime(2017, 6, 18),
        new DateTime(2019, 11, 22),
        new DateTime(2020, 9, 7)
    };

    // Eine Reihe mit einem Dezimalwert für jedes jeweilige Datum einfügen.
    // Die Daten werden entlang einer linearen X-Achse verteilt,
    // und die dieser Reihe hinzugefügten Werte erzeugen Datenpunkte.
    chart.Series.Add("Series 1", dates, new [] { 15.8, 21.5, 22.9, 28.7, 33.1 });

    Assert.AreEqual(ChartAxisType.Category, chart.AxisX.Type);
    Assert.AreEqual(ChartAxisType.Value, chart.AxisY.Type);

    // 3 - 2D-Streudiagramm:
    chart = AppendChart(builder, ChartType.Scatter, 500, 300);

    // Jede Reihe benötigt zwei Dezimalarrays gleicher Länge.
    // Das erste Array enthält X-Werte und das zweite enthält entsprechende Y-Werte
    // von Datenpunkten auf dem Diagramm des Diagramms.
    chart.Series.Add("Series 1", 
        new[] { 3.1, 3.5, 6.3, 4.1, 2.2, 8.3, 1.2, 3.6 }, 
        new[] { 3.1, 6.3, 4.6, 0.9, 8.5, 4.2, 2.3, 9.9 });
    chart.Series.Add("Series 2", 
        new[] { 2.6, 7.3, 4.5, 6.6, 2.1, 9.3, 0.7, 3.3 }, 
        new[] { 7.1, 6.6, 3.5, 7.8, 7.7, 9.5, 1.3, 4.6 });

    Assert.AreEqual(ChartAxisType.Value, chart.AxisX.Type);
    Assert.AreEqual(ChartAxisType.Value, chart.AxisY.Type);

    // 4 - Blasendiagramm:
    chart = AppendChart(builder, ChartType.Bubble, 500, 300);

    // Jede Reihe benötigt drei Dezimalarrays gleicher Länge.
    // Das erste Array enthält X-Werte, das zweite enthält entsprechende Y-Werte,
    // und der dritte enthält Durchmesser für jeden der Datenpunkte des Diagramms.
    chart.Series.Add("Series 1", 
        new [] { 1.1, 5.0, 9.8 }, 
        new [] { 1.2, 4.9, 9.9 }, 
        new [] { 2.0, 4.0, 8.0 });

    doc.Save(ArtifactsDir + "Charts.ChartSeriesCollection.docx");
}

/// <summary>
/// Fügen Sie ein Diagramm mit einem Document Builder mit einem bestimmten ChartType, Breite und Höhe ein und entfernen Sie seine Demodaten.
/// </summary>
private static Chart AppendChart(DocumentBuilder builder, ChartType chartType, double width, double height)
{
    Shape chartShape = builder.InsertChart(chartType, width, height);
    Chart chart = chartShape.Chart;
    chart.Series.Clear();
    return chart;
}
```

### Siehe auch

* class [ChartSeries](../../chartseries/)
* class [ChartSeriesCollection](../)
* namensraum [Aspose.Words.Drawing.Charts](../../chartseriescollection/)
* Montage [Aspose.Words](../../../)

---

## Add(string, double[], double[], double[]) {#add_1}

Fügt neu hinzu[`ChartSeries`](../../chartseries/) zu dieser Sammlung. Verwenden Sie diese Methode, um Serien zu jeder Art von Blasendiagramm hinzuzufügen.

```csharp
public ChartSeries Add(string seriesName, double[] xValues, double[] yValues, double[] bubbleSizes)
```

### Rückgabewert

Kürzlich hinzugefügt[`ChartSeries`](../../chartseries/) Objekt.

### Beispiele

Zeigt, wie ein geeigneter Typ von Diagrammreihen für einen Diagrammtyp erstellt wird.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Es gibt mehrere Möglichkeiten, die Seriensammlung eines Diagramms zu füllen.
    // Unterschiedliche Reihenschemata sind für unterschiedliche Diagrammtypen vorgesehen.
    // 1 - Säulendiagramm mit gruppierten und gebänderten Säulen entlang der X-Achse nach Kategorie:
    Chart chart = AppendChart(builder, ChartType.Column, 500, 300);

    string[] categories = { "Category 1", "Category 2", "Category 3" };

    // Fügen Sie zwei Reihen von Dezimalwerten ein, die einen Wert für jede entsprechende Kategorie enthalten.
    // Dieses Säulendiagramm hat drei Gruppen mit jeweils zwei Säulen.
    chart.Series.Add("Series 1", categories, new [] { 76.6, 82.1, 91.6 });
    chart.Series.Add("Series 2", categories, new [] { 64.2, 79.5, 94.0 });

    // Kategorien werden entlang der X-Achse verteilt und Werte werden entlang der Y-Achse verteilt.
    Assert.AreEqual(ChartAxisType.Category, chart.AxisX.Type);
    Assert.AreEqual(ChartAxisType.Value, chart.AxisY.Type);

    // 2 - Flächendiagramm mit Datumsangaben entlang der X-Achse:
    chart = AppendChart(builder, ChartType.Area, 500, 300);

    DateTime[] dates = { new DateTime(2014, 3, 31),
        new DateTime(2017, 1, 23),
        new DateTime(2017, 6, 18),
        new DateTime(2019, 11, 22),
        new DateTime(2020, 9, 7)
    };

    // Eine Reihe mit einem Dezimalwert für jedes jeweilige Datum einfügen.
    // Die Daten werden entlang einer linearen X-Achse verteilt,
    // und die dieser Reihe hinzugefügten Werte erzeugen Datenpunkte.
    chart.Series.Add("Series 1", dates, new [] { 15.8, 21.5, 22.9, 28.7, 33.1 });

    Assert.AreEqual(ChartAxisType.Category, chart.AxisX.Type);
    Assert.AreEqual(ChartAxisType.Value, chart.AxisY.Type);

    // 3 - 2D-Streudiagramm:
    chart = AppendChart(builder, ChartType.Scatter, 500, 300);

    // Jede Reihe benötigt zwei Dezimalarrays gleicher Länge.
    // Das erste Array enthält X-Werte und das zweite enthält entsprechende Y-Werte
    // von Datenpunkten auf dem Diagramm des Diagramms.
    chart.Series.Add("Series 1", 
        new[] { 3.1, 3.5, 6.3, 4.1, 2.2, 8.3, 1.2, 3.6 }, 
        new[] { 3.1, 6.3, 4.6, 0.9, 8.5, 4.2, 2.3, 9.9 });
    chart.Series.Add("Series 2", 
        new[] { 2.6, 7.3, 4.5, 6.6, 2.1, 9.3, 0.7, 3.3 }, 
        new[] { 7.1, 6.6, 3.5, 7.8, 7.7, 9.5, 1.3, 4.6 });

    Assert.AreEqual(ChartAxisType.Value, chart.AxisX.Type);
    Assert.AreEqual(ChartAxisType.Value, chart.AxisY.Type);

    // 4 - Blasendiagramm:
    chart = AppendChart(builder, ChartType.Bubble, 500, 300);

    // Jede Reihe benötigt drei Dezimalarrays gleicher Länge.
    // Das erste Array enthält X-Werte, das zweite enthält entsprechende Y-Werte,
    // und der dritte enthält Durchmesser für jeden der Datenpunkte des Diagramms.
    chart.Series.Add("Series 1", 
        new [] { 1.1, 5.0, 9.8 }, 
        new [] { 1.2, 4.9, 9.9 }, 
        new [] { 2.0, 4.0, 8.0 });

    doc.Save(ArtifactsDir + "Charts.ChartSeriesCollection.docx");
}

/// <summary>
/// Fügen Sie ein Diagramm mit einem Document Builder mit einem bestimmten ChartType, Breite und Höhe ein und entfernen Sie seine Demodaten.
/// </summary>
private static Chart AppendChart(DocumentBuilder builder, ChartType chartType, double width, double height)
{
    Shape chartShape = builder.InsertChart(chartType, width, height);
    Chart chart = chartShape.Chart;
    chart.Series.Clear();
    return chart;
}
```

### Siehe auch

* class [ChartSeries](../../chartseries/)
* class [ChartSeriesCollection](../)
* namensraum [Aspose.Words.Drawing.Charts](../../chartseriescollection/)
* Montage [Aspose.Words](../../../)


