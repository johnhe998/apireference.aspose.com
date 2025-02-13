---
title: Enum AxisTimeUnit
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Drawing.Charts.AxisTimeUnit enum. Specifica lunità di tempo per gli assi.
type: docs
weight: 590
url: /it/net/aspose.words.drawing.charts/axistimeunit/
---
## AxisTimeUnit enumeration

Specifica l'unità di tempo per gli assi.

```csharp
public enum AxisTimeUnit
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| Automatic | `0` | Specifica che l'unità non è stata impostata in modo esplicito e deve essere utilizzato il valore predefinito. |
| Days | `1` | Specifica che i dati del grafico devono essere visualizzati in giorni. |
| Months | `2` | Specifica che i dati del grafico devono essere visualizzati in mesi. |
| Years | `3` | Specifica che i dati del grafico devono essere visualizzati in anni. |

### Esempi

Mostra come inserire un grafico con valori di data/ora.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Line, 500, 300);
Chart chart = shape.Chart;

// Cancella la serie di dati demo del grafico per iniziare con un grafico pulito.
chart.Series.Clear();

// Aggiunge una serie personalizzata contenente valori di data/ora per l'asse X e rispettivi valori decimali per l'asse Y.
chart.Series.Add("Aspose Test Series",
    new[]
    {
        new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
        new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
    },
    new[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });

// Imposta i limiti inferiore e superiore per l'asse X.
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03));

// Imposta le unità principali dell'asse X su una settimana e le unità minori su un giorno.
xAxis.BaseTimeUnit = AxisTimeUnit.Days;
xAxis.MajorUnit = 7.0d;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorUnit = 1.0d;
xAxis.MinorTickMark = AxisTickMark.Outside;

// Definisce le proprietà dell'asse Y per i valori decimali.
ChartAxis yAxis = chart.AxisY;
yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100.0d;
yAxis.MinorUnit = 50.0d;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);

doc.Save(ArtifactsDir + "Charts.DateTimeValues.docx");
```

### Guarda anche

* spazio dei nomi [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* assemblea [Aspose.Words](../../)


