---
title: Chart.Legend
second_title: Aspose.Words für .NET-API-Referenz
description: Chart eigendom. Bietet Zugriff auf die Eigenschaften der Diagrammlegende.
type: docs
weight: 40
url: /de/net/aspose.words.drawing.charts/chart/legend/
---
## Chart.Legend property

Bietet Zugriff auf die Eigenschaften der Diagrammlegende.

```csharp
public ChartLegend Legend { get; }
```

### Beispiele

Zeigt, wie das Erscheinungsbild der Legende eines Diagramms bearbeitet wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Line, 450, 300);
Chart chart = shape.Chart;

Assert.AreEqual(3, chart.Series.Count);
Assert.AreEqual("Series 1", chart.Series[0].Name);
Assert.AreEqual("Series 2", chart.Series[1].Name);
Assert.AreEqual("Series 3", chart.Series[2].Name);

// Bewegen Sie die Legende des Diagramms in die obere rechte Ecke.
ChartLegend legend = chart.Legend;
legend.Position = LegendPosition.TopRight;

// Geben Sie anderen Diagrammelementen wie dem Diagramm mehr Platz, indem Sie ihnen erlauben, die Legende zu überlappen.
legend.Overlay = true;

doc.Save(ArtifactsDir + "Charts.ChartLegend.docx");
```

### Siehe auch

* class [ChartLegend](../../chartlegend/)
* class [Chart](../)
* namensraum [Aspose.Words.Drawing.Charts](../../chart/)
* Montage [Aspose.Words](../../../)


