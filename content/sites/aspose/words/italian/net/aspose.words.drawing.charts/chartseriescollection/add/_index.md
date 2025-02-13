---
title: ChartSeriesCollection.Add
second_title: Aspose.Words per .NET API Reference
description: ChartSeriesCollection metodo. Aggiunge nuovoChartSeries questa raccolta. Utilizzare questo metodo per aggiungere serie a qualsiasi tipo di grafici a barre colonne linee e superfici.
type: docs
weight: 30
url: /it/net/aspose.words.drawing.charts/chartseriescollection/add/
---
## Add(string, string[], double[]) {#add_3}

Aggiunge nuovo[`ChartSeries`](../../chartseries/) questa raccolta. Utilizzare questo metodo per aggiungere serie a qualsiasi tipo di grafici a barre, colonne, linee e superfici.

```csharp
public ChartSeries Add(string seriesName, string[] categories, double[] values)
```

### Valore di ritorno

Aggiunto recentemente[`ChartSeries`](../../chartseries/) oggetto.

### Esempi

Mostra come creare un tipo appropriato di serie di grafici per un tipo di grafico.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Esistono diversi modi per popolare la raccolta di serie di un grafico.
    // Schemi di serie differenti sono destinati a tipi di grafici differenti.
    // 1 - Grafico a colonne con colonne raggruppate e raggruppate lungo l'asse X per categoria:
    Chart chart = AppendChart(builder, ChartType.Column, 500, 300);

    string[] categories = { "Category 1", "Category 2", "Category 3" };

    // Inserisce due serie di valori decimali contenenti un valore per ciascuna rispettiva categoria.
    // Questo istogramma avrà tre gruppi, ciascuno con due colonne.
    chart.Series.Add("Series 1", categories, new [] { 76.6, 82.1, 91.6 });
    chart.Series.Add("Series 2", categories, new [] { 64.2, 79.5, 94.0 });

    // Le categorie sono distribuite lungo l'asse X e i valori sono distribuiti lungo l'asse Y.
    Assert.AreEqual(ChartAxisType.Category, chart.AxisX.Type);
    Assert.AreEqual(ChartAxisType.Value, chart.AxisY.Type);

    // 2 - Grafico ad area con date distribuite lungo l'asse X:
    chart = AppendChart(builder, ChartType.Area, 500, 300);

    DateTime[] dates = { new DateTime(2014, 3, 31),
        new DateTime(2017, 1, 23),
        new DateTime(2017, 6, 18),
        new DateTime(2019, 11, 22),
        new DateTime(2020, 9, 7)
    };

    // Inserisce una serie con un valore decimale per ogni rispettiva data.
    // Le date saranno distribuite lungo un asse X lineare,
    // e i valori aggiunti a questa serie creeranno punti dati.
    chart.Series.Add("Series 1", dates, new [] { 15.8, 21.5, 22.9, 28.7, 33.1 });

    Assert.AreEqual(ChartAxisType.Category, chart.AxisX.Type);
    Assert.AreEqual(ChartAxisType.Value, chart.AxisY.Type);

    // 3 - Grafico a dispersione 2D:
    chart = AppendChart(builder, ChartType.Scatter, 500, 300);

    // Ogni serie avrà bisogno di due array decimali di uguale lunghezza.
    // Il primo array contiene i valori X e il secondo i valori Y corrispondenti
    // di punti dati sul grafico del grafico.
    chart.Series.Add("Series 1", 
        new[] { 3.1, 3.5, 6.3, 4.1, 2.2, 8.3, 1.2, 3.6 }, 
        new[] { 3.1, 6.3, 4.6, 0.9, 8.5, 4.2, 2.3, 9.9 });
    chart.Series.Add("Series 2", 
        new[] { 2.6, 7.3, 4.5, 6.6, 2.1, 9.3, 0.7, 3.3 }, 
        new[] { 7.1, 6.6, 3.5, 7.8, 7.7, 9.5, 1.3, 4.6 });

    Assert.AreEqual(ChartAxisType.Value, chart.AxisX.Type);
    Assert.AreEqual(ChartAxisType.Value, chart.AxisY.Type);

    // 4 - Grafico a bolle:
    chart = AppendChart(builder, ChartType.Bubble, 500, 300);

    // Ogni serie avrà bisogno di tre array decimali di uguale lunghezza.
    // Il primo array contiene valori X, il secondo contiene valori Y corrispondenti,
    // e il terzo contiene i diametri per ciascuno dei punti dati del grafico.
    chart.Series.Add("Series 1", 
        new [] { 1.1, 5.0, 9.8 }, 
        new [] { 1.2, 4.9, 9.9 }, 
        new [] { 2.0, 4.0, 8.0 });

    doc.Save(ArtifactsDir + "Charts.ChartSeriesCollection.docx");
}

/// <summary>
/// Inserisci un grafico utilizzando un generatore di documenti di un ChartType, larghezza e altezza specificati e rimuovi i suoi dati demo.
/// </summary>
private static Chart AppendChart(DocumentBuilder builder, ChartType chartType, double width, double height)
{
    Shape chartShape = builder.InsertChart(chartType, width, height);
    Chart chart = chartShape.Chart;
    chart.Series.Clear();
    return chart;
}
```

### Guarda anche

* class [ChartSeries](../../chartseries/)
* class [ChartSeriesCollection](../)
* spazio dei nomi [Aspose.Words.Drawing.Charts](../../chartseriescollection/)
* assemblea [Aspose.Words](../../../)

---

## Add(string, double[], double[]) {#add}

Aggiunge nuovo[`ChartSeries`](../../chartseries/) a questa raccolta. Utilizzare questo metodo per aggiungere serie a qualsiasi tipo di grafici a dispersione.

```csharp
public ChartSeries Add(string seriesName, double[] xValues, double[] yValues)
```

### Valore di ritorno

Aggiunto recentemente[`ChartSeries`](../../chartseries/) oggetto.

### Esempi

Mostra come creare un tipo appropriato di serie di grafici per un tipo di grafico.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Esistono diversi modi per popolare la raccolta di serie di un grafico.
    // Schemi di serie differenti sono destinati a tipi di grafici differenti.
    // 1 - Grafico a colonne con colonne raggruppate e raggruppate lungo l'asse X per categoria:
    Chart chart = AppendChart(builder, ChartType.Column, 500, 300);

    string[] categories = { "Category 1", "Category 2", "Category 3" };

    // Inserisce due serie di valori decimali contenenti un valore per ciascuna rispettiva categoria.
    // Questo istogramma avrà tre gruppi, ciascuno con due colonne.
    chart.Series.Add("Series 1", categories, new [] { 76.6, 82.1, 91.6 });
    chart.Series.Add("Series 2", categories, new [] { 64.2, 79.5, 94.0 });

    // Le categorie sono distribuite lungo l'asse X e i valori sono distribuiti lungo l'asse Y.
    Assert.AreEqual(ChartAxisType.Category, chart.AxisX.Type);
    Assert.AreEqual(ChartAxisType.Value, chart.AxisY.Type);

    // 2 - Grafico ad area con date distribuite lungo l'asse X:
    chart = AppendChart(builder, ChartType.Area, 500, 300);

    DateTime[] dates = { new DateTime(2014, 3, 31),
        new DateTime(2017, 1, 23),
        new DateTime(2017, 6, 18),
        new DateTime(2019, 11, 22),
        new DateTime(2020, 9, 7)
    };

    // Inserisce una serie con un valore decimale per ogni rispettiva data.
    // Le date saranno distribuite lungo un asse X lineare,
    // e i valori aggiunti a questa serie creeranno punti dati.
    chart.Series.Add("Series 1", dates, new [] { 15.8, 21.5, 22.9, 28.7, 33.1 });

    Assert.AreEqual(ChartAxisType.Category, chart.AxisX.Type);
    Assert.AreEqual(ChartAxisType.Value, chart.AxisY.Type);

    // 3 - Grafico a dispersione 2D:
    chart = AppendChart(builder, ChartType.Scatter, 500, 300);

    // Ogni serie avrà bisogno di due array decimali di uguale lunghezza.
    // Il primo array contiene i valori X e il secondo i valori Y corrispondenti
    // di punti dati sul grafico del grafico.
    chart.Series.Add("Series 1", 
        new[] { 3.1, 3.5, 6.3, 4.1, 2.2, 8.3, 1.2, 3.6 }, 
        new[] { 3.1, 6.3, 4.6, 0.9, 8.5, 4.2, 2.3, 9.9 });
    chart.Series.Add("Series 2", 
        new[] { 2.6, 7.3, 4.5, 6.6, 2.1, 9.3, 0.7, 3.3 }, 
        new[] { 7.1, 6.6, 3.5, 7.8, 7.7, 9.5, 1.3, 4.6 });

    Assert.AreEqual(ChartAxisType.Value, chart.AxisX.Type);
    Assert.AreEqual(ChartAxisType.Value, chart.AxisY.Type);

    // 4 - Grafico a bolle:
    chart = AppendChart(builder, ChartType.Bubble, 500, 300);

    // Ogni serie avrà bisogno di tre array decimali di uguale lunghezza.
    // Il primo array contiene valori X, il secondo contiene valori Y corrispondenti,
    // e il terzo contiene i diametri per ciascuno dei punti dati del grafico.
    chart.Series.Add("Series 1", 
        new [] { 1.1, 5.0, 9.8 }, 
        new [] { 1.2, 4.9, 9.9 }, 
        new [] { 2.0, 4.0, 8.0 });

    doc.Save(ArtifactsDir + "Charts.ChartSeriesCollection.docx");
}

/// <summary>
/// Inserisci un grafico utilizzando un generatore di documenti di un ChartType, larghezza e altezza specificati e rimuovi i suoi dati demo.
/// </summary>
private static Chart AppendChart(DocumentBuilder builder, ChartType chartType, double width, double height)
{
    Shape chartShape = builder.InsertChart(chartType, width, height);
    Chart chart = chartShape.Chart;
    chart.Series.Clear();
    return chart;
}
```

### Guarda anche

* class [ChartSeries](../../chartseries/)
* class [ChartSeriesCollection](../)
* spazio dei nomi [Aspose.Words.Drawing.Charts](../../chartseriescollection/)
* assemblea [Aspose.Words](../../../)

---

## Add(string, DateTime[], double[]) {#add_2}

Aggiunge nuovo[`ChartSeries`](../../chartseries/) a questa raccolta. Usa questo metodo per aggiungere serie a qualsiasi tipo di grafico Area, Radar e Stock.

```csharp
public ChartSeries Add(string seriesName, DateTime[] dates, double[] values)
```

### Esempi

Mostra come creare un tipo appropriato di serie di grafici per un tipo di grafico.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Esistono diversi modi per popolare la raccolta di serie di un grafico.
    // Schemi di serie differenti sono destinati a tipi di grafici differenti.
    // 1 - Grafico a colonne con colonne raggruppate e raggruppate lungo l'asse X per categoria:
    Chart chart = AppendChart(builder, ChartType.Column, 500, 300);

    string[] categories = { "Category 1", "Category 2", "Category 3" };

    // Inserisce due serie di valori decimali contenenti un valore per ciascuna rispettiva categoria.
    // Questo istogramma avrà tre gruppi, ciascuno con due colonne.
    chart.Series.Add("Series 1", categories, new [] { 76.6, 82.1, 91.6 });
    chart.Series.Add("Series 2", categories, new [] { 64.2, 79.5, 94.0 });

    // Le categorie sono distribuite lungo l'asse X e i valori sono distribuiti lungo l'asse Y.
    Assert.AreEqual(ChartAxisType.Category, chart.AxisX.Type);
    Assert.AreEqual(ChartAxisType.Value, chart.AxisY.Type);

    // 2 - Grafico ad area con date distribuite lungo l'asse X:
    chart = AppendChart(builder, ChartType.Area, 500, 300);

    DateTime[] dates = { new DateTime(2014, 3, 31),
        new DateTime(2017, 1, 23),
        new DateTime(2017, 6, 18),
        new DateTime(2019, 11, 22),
        new DateTime(2020, 9, 7)
    };

    // Inserisce una serie con un valore decimale per ogni rispettiva data.
    // Le date saranno distribuite lungo un asse X lineare,
    // e i valori aggiunti a questa serie creeranno punti dati.
    chart.Series.Add("Series 1", dates, new [] { 15.8, 21.5, 22.9, 28.7, 33.1 });

    Assert.AreEqual(ChartAxisType.Category, chart.AxisX.Type);
    Assert.AreEqual(ChartAxisType.Value, chart.AxisY.Type);

    // 3 - Grafico a dispersione 2D:
    chart = AppendChart(builder, ChartType.Scatter, 500, 300);

    // Ogni serie avrà bisogno di due array decimali di uguale lunghezza.
    // Il primo array contiene i valori X e il secondo i valori Y corrispondenti
    // di punti dati sul grafico del grafico.
    chart.Series.Add("Series 1", 
        new[] { 3.1, 3.5, 6.3, 4.1, 2.2, 8.3, 1.2, 3.6 }, 
        new[] { 3.1, 6.3, 4.6, 0.9, 8.5, 4.2, 2.3, 9.9 });
    chart.Series.Add("Series 2", 
        new[] { 2.6, 7.3, 4.5, 6.6, 2.1, 9.3, 0.7, 3.3 }, 
        new[] { 7.1, 6.6, 3.5, 7.8, 7.7, 9.5, 1.3, 4.6 });

    Assert.AreEqual(ChartAxisType.Value, chart.AxisX.Type);
    Assert.AreEqual(ChartAxisType.Value, chart.AxisY.Type);

    // 4 - Grafico a bolle:
    chart = AppendChart(builder, ChartType.Bubble, 500, 300);

    // Ogni serie avrà bisogno di tre array decimali di uguale lunghezza.
    // Il primo array contiene valori X, il secondo contiene valori Y corrispondenti,
    // e il terzo contiene i diametri per ciascuno dei punti dati del grafico.
    chart.Series.Add("Series 1", 
        new [] { 1.1, 5.0, 9.8 }, 
        new [] { 1.2, 4.9, 9.9 }, 
        new [] { 2.0, 4.0, 8.0 });

    doc.Save(ArtifactsDir + "Charts.ChartSeriesCollection.docx");
}

/// <summary>
/// Inserisci un grafico utilizzando un generatore di documenti di un ChartType, larghezza e altezza specificati e rimuovi i suoi dati demo.
/// </summary>
private static Chart AppendChart(DocumentBuilder builder, ChartType chartType, double width, double height)
{
    Shape chartShape = builder.InsertChart(chartType, width, height);
    Chart chart = chartShape.Chart;
    chart.Series.Clear();
    return chart;
}
```

### Guarda anche

* class [ChartSeries](../../chartseries/)
* class [ChartSeriesCollection](../)
* spazio dei nomi [Aspose.Words.Drawing.Charts](../../chartseriescollection/)
* assemblea [Aspose.Words](../../../)

---

## Add(string, double[], double[], double[]) {#add_1}

Aggiunge nuovo[`ChartSeries`](../../chartseries/) a questa raccolta. Usa questo metodo per aggiungere serie a qualsiasi tipo di grafici a bolle.

```csharp
public ChartSeries Add(string seriesName, double[] xValues, double[] yValues, double[] bubbleSizes)
```

### Valore di ritorno

Aggiunto recentemente[`ChartSeries`](../../chartseries/) oggetto.

### Esempi

Mostra come creare un tipo appropriato di serie di grafici per un tipo di grafico.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Esistono diversi modi per popolare la raccolta di serie di un grafico.
    // Schemi di serie differenti sono destinati a tipi di grafici differenti.
    // 1 - Grafico a colonne con colonne raggruppate e raggruppate lungo l'asse X per categoria:
    Chart chart = AppendChart(builder, ChartType.Column, 500, 300);

    string[] categories = { "Category 1", "Category 2", "Category 3" };

    // Inserisce due serie di valori decimali contenenti un valore per ciascuna rispettiva categoria.
    // Questo istogramma avrà tre gruppi, ciascuno con due colonne.
    chart.Series.Add("Series 1", categories, new [] { 76.6, 82.1, 91.6 });
    chart.Series.Add("Series 2", categories, new [] { 64.2, 79.5, 94.0 });

    // Le categorie sono distribuite lungo l'asse X e i valori sono distribuiti lungo l'asse Y.
    Assert.AreEqual(ChartAxisType.Category, chart.AxisX.Type);
    Assert.AreEqual(ChartAxisType.Value, chart.AxisY.Type);

    // 2 - Grafico ad area con date distribuite lungo l'asse X:
    chart = AppendChart(builder, ChartType.Area, 500, 300);

    DateTime[] dates = { new DateTime(2014, 3, 31),
        new DateTime(2017, 1, 23),
        new DateTime(2017, 6, 18),
        new DateTime(2019, 11, 22),
        new DateTime(2020, 9, 7)
    };

    // Inserisce una serie con un valore decimale per ogni rispettiva data.
    // Le date saranno distribuite lungo un asse X lineare,
    // e i valori aggiunti a questa serie creeranno punti dati.
    chart.Series.Add("Series 1", dates, new [] { 15.8, 21.5, 22.9, 28.7, 33.1 });

    Assert.AreEqual(ChartAxisType.Category, chart.AxisX.Type);
    Assert.AreEqual(ChartAxisType.Value, chart.AxisY.Type);

    // 3 - Grafico a dispersione 2D:
    chart = AppendChart(builder, ChartType.Scatter, 500, 300);

    // Ogni serie avrà bisogno di due array decimali di uguale lunghezza.
    // Il primo array contiene i valori X e il secondo i valori Y corrispondenti
    // di punti dati sul grafico del grafico.
    chart.Series.Add("Series 1", 
        new[] { 3.1, 3.5, 6.3, 4.1, 2.2, 8.3, 1.2, 3.6 }, 
        new[] { 3.1, 6.3, 4.6, 0.9, 8.5, 4.2, 2.3, 9.9 });
    chart.Series.Add("Series 2", 
        new[] { 2.6, 7.3, 4.5, 6.6, 2.1, 9.3, 0.7, 3.3 }, 
        new[] { 7.1, 6.6, 3.5, 7.8, 7.7, 9.5, 1.3, 4.6 });

    Assert.AreEqual(ChartAxisType.Value, chart.AxisX.Type);
    Assert.AreEqual(ChartAxisType.Value, chart.AxisY.Type);

    // 4 - Grafico a bolle:
    chart = AppendChart(builder, ChartType.Bubble, 500, 300);

    // Ogni serie avrà bisogno di tre array decimali di uguale lunghezza.
    // Il primo array contiene valori X, il secondo contiene valori Y corrispondenti,
    // e il terzo contiene i diametri per ciascuno dei punti dati del grafico.
    chart.Series.Add("Series 1", 
        new [] { 1.1, 5.0, 9.8 }, 
        new [] { 1.2, 4.9, 9.9 }, 
        new [] { 2.0, 4.0, 8.0 });

    doc.Save(ArtifactsDir + "Charts.ChartSeriesCollection.docx");
}

/// <summary>
/// Inserisci un grafico utilizzando un generatore di documenti di un ChartType, larghezza e altezza specificati e rimuovi i suoi dati demo.
/// </summary>
private static Chart AppendChart(DocumentBuilder builder, ChartType chartType, double width, double height)
{
    Shape chartShape = builder.InsertChart(chartType, width, height);
    Chart chart = chartShape.Chart;
    chart.Series.Clear();
    return chart;
}
```

### Guarda anche

* class [ChartSeries](../../chartseries/)
* class [ChartSeriesCollection](../)
* spazio dei nomi [Aspose.Words.Drawing.Charts](../../chartseriescollection/)
* assemblea [Aspose.Words](../../../)


