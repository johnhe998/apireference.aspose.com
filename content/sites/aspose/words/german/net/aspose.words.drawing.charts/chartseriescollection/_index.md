---
title: Class ChartSeriesCollection
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Drawing.Charts.ChartSeriesCollection klas. Repräsentiert Sammlung von aChartSeries .
type: docs
weight: 740
url: /de/net/aspose.words.drawing.charts/chartseriescollection/
---
## ChartSeriesCollection class

Repräsentiert Sammlung von a[`ChartSeries`](../chartseries/) .

```csharp
public class ChartSeriesCollection : IEnumerable<ChartSeries>
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [Count](../../aspose.words.drawing.charts/chartseriescollection/count/) { get; } | Gibt die Anzahl von zurück[`ChartSeries`](../chartseries/) in dieser Sammlung. |
| [Item](../../aspose.words.drawing.charts/chartseriescollection/item/) { get; } | Gibt a zurück[`ChartSeries`](../chartseries/) am angegebenen Index. |

## Methoden

| Name | Beschreibung |
| --- | --- |
| [Add](../../aspose.words.drawing.charts/chartseriescollection/add/#add_2)(string, DateTime[], double[]) | Fügt neu hinzu[`ChartSeries`](../chartseries/) zu dieser Sammlung. Verwenden Sie diese Methode, um Serien zu jeder Art von Flächen-, Radar- und Aktiendiagrammen hinzuzufügen. |
| [Add](../../aspose.words.drawing.charts/chartseriescollection/add/#add)(string, double[], double[]) | Fügt neu hinzu[`ChartSeries`](../chartseries/) zu dieser Sammlung hinzufügen. Verwenden Sie diese Methode, um Serien zu jeder Art von Streudiagrammen hinzuzufügen. |
| [Add](../../aspose.words.drawing.charts/chartseriescollection/add/#add_3)(string, string[], double[]) | Fügt neu hinzu[`ChartSeries`](../chartseries/)zu dieser Sammlung hinzufügen. Verwenden Sie diese Methode, um Serien zu jeder Art von Balken-, Säulen-, Linien- und Oberflächendiagrammen hinzuzufügen. |
| [Add](../../aspose.words.drawing.charts/chartseriescollection/add/#add_1)(string, double[], double[], double[]) | Fügt neu hinzu[`ChartSeries`](../chartseries/) zu dieser Sammlung. Verwenden Sie diese Methode, um Serien zu jeder Art von Blasendiagramm hinzuzufügen. |
| [Clear](../../aspose.words.drawing.charts/chartseriescollection/clear/)() | Entfernt alle[`ChartSeries`](../chartseries/) aus dieser Sammlung. |
| [GetEnumerator](../../aspose.words.drawing.charts/chartseriescollection/getenumerator/)() | Gibt ein Aufzählungsobjekt zurück. |
| [RemoveAt](../../aspose.words.drawing.charts/chartseriescollection/removeat/)(int) | Entfernt a[`ChartSeries`](../chartseries/) am angegebenen Index. |

### Beispiele

Zeigt, wie Reihendaten in einem Diagramm hinzugefügt und entfernt werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie ein Säulendiagramm ein, das standardmäßig drei Reihen von Demodaten enthält.
Shape chartShape = builder.InsertChart(ChartType.Column, 400, 300);
Chart chart = chartShape.Chart;

// Jede Reihe hat vier Dezimalwerte: einen für jede der vier Kategorien.
// Vier Cluster aus drei Spalten repräsentieren diese Daten.
ChartSeriesCollection chartData = chart.Series;

Assert.AreEqual(3, chartData.Count);

// Drucken Sie den Namen jeder Serie im Diagramm.
using (IEnumerator<ChartSeries> enumerator = chart.Series.GetEnumerator())
{
    while (enumerator.MoveNext())
    {
        Console.WriteLine(enumerator.Current.Name);
    }
}

// Dies sind die Namen der Kategorien im Diagramm.
string[] categories = { "Category 1", "Category 2", "Category 3", "Category 4" };

// Wir können eine Reihe mit neuen Werten für bestehende Kategorien hinzufügen.
// Dieses Diagramm enthält nun vier Cluster mit vier Spalten.
chart.Series.Add("Series 4", categories, new[] { 4.4, 7.0, 3.5, 2.1 });

// Eine Chartserie kann auch per Index entfernt werden, wie hier.
// Dadurch wird eine der drei Demo-Serien entfernt, die mit dem Diagramm geliefert wurden.
chartData.RemoveAt(2);

Assert.False(chartData.Any(s => s.Name == "Series 3"));

// Mit dieser Methode können wir auch alle Daten des Diagramms auf einmal löschen.
// Beim Erstellen eines neuen Diagramms werden auf diese Weise alle Demodaten gelöscht
// bevor wir mit der Arbeit an einem leeren Diagramm beginnen können.
chartData.Clear();
```

### Siehe auch

* class [ChartSeries](../chartseries/)
* namensraum [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* Montage [Aspose.Words](../../)


