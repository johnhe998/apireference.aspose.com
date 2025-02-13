---
title: ChartTitle.Show
second_title: Aspose.Words för .NET API Referens
description: ChartTitle fast egendom. Bestämmer om titeln ska visas för detta diagram. Standardvärdet är sant.
type: docs
weight: 20
url: /sv/net/aspose.words.drawing.charts/charttitle/show/
---
## ChartTitle.Show property

Bestämmer om titeln ska visas för detta diagram. Standardvärdet är sant.

```csharp
public bool Show { get; set; }
```

### Exempel

Visar hur man infogar ett diagram och ställer in en titel.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Infoga en diagramform med en dokumentbyggare och få dess diagram.
Shape chartShape = builder.InsertChart(ChartType.Bar, 400, 300);
Chart chart = chartShape.Chart;

// Använd egenskapen "Titel" för att ge vårt diagram en titel, som visas högst upp i mitten av diagramområdet.
ChartTitle title = chart.Title;
title.Text = "My Chart";

  // Ställ in egenskapen "Show" till "true" för att göra titeln synlig.
title.Show = true;

// Ställ in egenskapen "Overlay" på "true" Ge andra diagramelement mer utrymme genom att tillåta dem att överlappa titeln
title.Overlay = true;

doc.Save(ArtifactsDir + "Charts.ChartTitle.docx");
```

### Se även

* class [ChartTitle](../)
* namnutrymme [Aspose.Words.Drawing.Charts](../../charttitle/)
* hopsättning [Aspose.Words](../../../)


