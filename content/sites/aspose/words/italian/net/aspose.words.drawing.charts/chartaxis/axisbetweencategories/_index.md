---
title: ChartAxis.AxisBetweenCategories
second_title: Aspose.Words per .NET API Reference
description: ChartAxis proprietà. Ottiene o imposta un flag che indica se lasse dei valori incrocia lasse delle categorie tra le categorie.
type: docs
weight: 10
url: /it/net/aspose.words.drawing.charts/chartaxis/axisbetweencategories/
---
## ChartAxis.AxisBetweenCategories property

Ottiene o imposta un flag che indica se l'asse dei valori incrocia l'asse delle categorie tra le categorie.

```csharp
public bool AxisBetweenCategories { get; set; }
```

### Osservazioni

La proprietà ha effetto solo per gli assi dei valori. Non è supportato dai nuovi grafici di MS Office 2016.

### Esempi

Mostra come far incrociare un asse del grafico in una posizione personalizzata.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Column, 450, 250);
Chart chart = shape.Chart;

Assert.AreEqual(3, chart.Series.Count);
Assert.AreEqual("Series 1", chart.Series[0].Name);
Assert.AreEqual("Series 2", chart.Series[1].Name);
Assert.AreEqual("Series 3", chart.Series[2].Name);

// Per gli istogrammi, l'asse Y incrocia lo zero per impostazione predefinita,
// il che significa che le colonne per tutti i valori inferiori allo zero puntano verso il basso per rappresentare valori negativi.
// Possiamo impostare un valore diverso per l'incrocio dell'asse Y. In questo caso, lo imposteremo a 3.
ChartAxis axis = chart.AxisX;
axis.Crosses = AxisCrosses.Custom;
axis.CrossesAt = 3;
axis.AxisBetweenCategories = true;

doc.Save(ArtifactsDir + "Charts.AxisCross.docx");
```

### Guarda anche

* class [ChartAxis](../)
* spazio dei nomi [Aspose.Words.Drawing.Charts](../../chartaxis/)
* assemblea [Aspose.Words](../../../)


