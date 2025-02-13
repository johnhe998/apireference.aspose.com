---
title: ChartNumberFormat.IsLinkedToSource
second_title: Aspose.Words per .NET API Reference
description: ChartNumberFormat proprietà. Specifica se il codice del formato è collegato a una cella di origine. Limpostazione predefinita è true.
type: docs
weight: 20
url: /it/net/aspose.words.drawing.charts/chartnumberformat/islinkedtosource/
---
## ChartNumberFormat.IsLinkedToSource property

Specifica se il codice del formato è collegato a una cella di origine. L'impostazione predefinita è true.

```csharp
public bool IsLinkedToSource { get; set; }
```

### Osservazioni

Il NumberFormat verrà reimpostato su generale se il codice del formato è collegato all'origine.

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

* class [ChartNumberFormat](../)
* spazio dei nomi [Aspose.Words.Drawing.Charts](../../chartnumberformat/)
* assemblea [Aspose.Words](../../../)


