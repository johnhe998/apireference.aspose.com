---
title: Class ChartNumberFormat
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Drawing.Charts.ChartNumberFormat classe. Rappresenta la formattazione del numero dellelemento padre.
type: docs
weight: 720
url: /it/net/aspose.words.drawing.charts/chartnumberformat/
---
## ChartNumberFormat class

Rappresenta la formattazione del numero dell'elemento padre.

```csharp
public class ChartNumberFormat
```

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [FormatCode](../../aspose.words.drawing.charts/chartnumberformat/formatcode/) { get; set; } | Ottiene o imposta il codice del formato applicato a un'etichetta dati. |
| [IsLinkedToSource](../../aspose.words.drawing.charts/chartnumberformat/islinkedtosource/) { get; set; } | Specifica se il codice del formato è collegato a una cella di origine. L'impostazione predefinita è true. |

### Esempi

Mostra come impostare la formattazione per i valori del grafico.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Column, 500, 300);
Chart chart = shape.Chart;

// Cancella la serie di dati demo del grafico per iniziare con un grafico pulito.
chart.Series.Clear();

// Aggiungi una serie personalizzata al grafico con le categorie per l'asse X,
 // e valori numerici grandi rispettivi per l'asse Y.
chart.Series.Add("Aspose Test Series",
    new [] { "Word", "PDF", "Excel", "GoogleDocs", "Note" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });

 // Imposta il formato numerico delle etichette di graduazione dell'asse Y in modo da non raggruppare le cifre con le virgole.
chart.AxisY.NumberFormat.FormatCode = "#,##0";

// Questo flag può sovrascrivere il valore sopra e disegnare il formato numerico dalla cella di origine.
Assert.False(chart.AxisY.NumberFormat.IsLinkedToSource);

doc.Save(ArtifactsDir + "Charts.SetNumberFormatToChartAxis.docx");
```

### Guarda anche

* spazio dei nomi [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* assemblea [Aspose.Words](../../)


