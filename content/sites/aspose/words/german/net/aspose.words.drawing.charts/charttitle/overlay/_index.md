---
title: ChartTitle.Overlay
second_title: Aspose.Words für .NET-API-Referenz
description: ChartTitle eigendom. Legt fest ob andere Diagrammelemente den Titel überlappen dürfen. Standardmäßig ist Überlagerung falsch.
type: docs
weight: 10
url: /de/net/aspose.words.drawing.charts/charttitle/overlay/
---
## ChartTitle.Overlay property

Legt fest, ob andere Diagrammelemente den Titel überlappen dürfen. Standardmäßig ist Überlagerung falsch.

```csharp
public bool Overlay { get; set; }
```

### Beispiele

Zeigt, wie Sie ein Diagramm einfügen und einen Titel festlegen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie eine Diagrammform mit einem Dokumentenersteller ein und erhalten Sie ihr Diagramm.
Shape chartShape = builder.InsertChart(ChartType.Bar, 400, 300);
Chart chart = chartShape.Chart;

// Verwenden Sie die Eigenschaft "Titel", um unserem Diagramm einen Titel zu geben, der oben in der Mitte des Diagrammbereichs angezeigt wird.
ChartTitle title = chart.Title;
title.Text = "My Chart";

 // Setzen Sie die Eigenschaft "Show" auf "true", um den Titel sichtbar zu machen.
title.Show = true;

// Setzen Sie die Eigenschaft "Overlay" auf "true". Geben Sie anderen Diagrammelementen mehr Platz, indem Sie ihnen erlauben, den Titel zu überlappen
title.Overlay = true;

doc.Save(ArtifactsDir + "Charts.ChartTitle.docx");
```

### Siehe auch

* class [ChartTitle](../)
* namensraum [Aspose.Words.Drawing.Charts](../../charttitle/)
* Montage [Aspose.Words](../../../)


