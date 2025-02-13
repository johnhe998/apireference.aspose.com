---
title: Class ChartTitle
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Drawing.Charts.ChartTitle classe. Fornisce laccesso alle proprietà del titolo del grafico.
type: docs
weight: 750
url: /it/net/aspose.words.drawing.charts/charttitle/
---
## ChartTitle class

Fornisce l'accesso alle proprietà del titolo del grafico.

```csharp
public class ChartTitle
```

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [Overlay](../../aspose.words.drawing.charts/charttitle/overlay/) { get; set; } | Determina se altri elementi del grafico possono sovrapporsi al titolo. Per impostazione predefinita, la sovrapposizione è falsa. |
| [Show](../../aspose.words.drawing.charts/charttitle/show/) { get; set; } | Determina se il titolo deve essere mostrato per questo grafico. Il valore predefinito è true. |
| [Text](../../aspose.words.drawing.charts/charttitle/text/) { get; set; } | Ottiene o imposta il testo del titolo del grafico. Se viene specificato un valore nullo o vuoto, verrà mostrato il titolo generato automaticamente. |

### Esempi

Mostra come inserire un grafico e impostare un titolo.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserisci una forma di grafico con un generatore di documenti e ottieni il suo grafico.
Shape chartShape = builder.InsertChart(ChartType.Bar, 400, 300);
Chart chart = chartShape.Chart;

// Usa la proprietà "Titolo" per assegnare un titolo al nostro grafico, che appare in alto al centro dell'area del grafico.
ChartTitle title = chart.Title;
title.Text = "My Chart";

 // Imposta la proprietà "Mostra" su "true" per rendere visibile il titolo.
title.Show = true;

// Imposta la proprietà "Overlay" su "true" Assegna più spazio agli altri elementi del grafico consentendo loro di sovrapporsi al titolo
title.Overlay = true;

doc.Save(ArtifactsDir + "Charts.ChartTitle.docx");
```

### Guarda anche

* spazio dei nomi [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* assemblea [Aspose.Words](../../)


