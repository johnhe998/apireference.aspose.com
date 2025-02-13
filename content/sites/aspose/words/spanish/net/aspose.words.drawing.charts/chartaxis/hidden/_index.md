---
title: ChartAxis.Hidden
second_title: Referencia de API de Aspose.Words para .NET
description: ChartAxis propiedad. Obtiene o establece un indicador que indica si este eje está oculto o no.
type: docs
weight: 80
url: /es/net/aspose.words.drawing.charts/chartaxis/hidden/
---
## ChartAxis.Hidden property

Obtiene o establece un indicador que indica si este eje está oculto o no.

```csharp
public bool Hidden { get; set; }
```

### Observaciones

El valor predeterminado es **falso** .

### Ejemplos

Muestra cómo ocultar los ejes del gráfico.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Line, 500, 300);
Chart chart = shape.Chart;

// Borre la serie de datos de demostración del gráfico para comenzar con un gráfico limpio.
chart.Series.Clear();

// Agregar una serie personalizada con categorías para el eje X y valores decimales respectivos para el eje Y.
chart.Series.Add("AW Series 1",
    new[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new[] { 1.2, 0.3, 2.1, 2.9, 4.2 });

  // Oculte los ejes del gráfico para simplificar la apariencia del gráfico.
chart.AxisX.Hidden = true;
chart.AxisY.Hidden = true;

doc.Save(ArtifactsDir + "Charts.HideChartAxis.docx");
```

### Ver también

* class [ChartAxis](../)
* espacio de nombres [Aspose.Words.Drawing.Charts](../../chartaxis/)
* asamblea [Aspose.Words](../../../)


