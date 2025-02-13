---
title: Enum AxisTickLabelPosition
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Drawing.Charts.AxisTickLabelPosition enumeración. Especifica las posiciones posibles para las etiquetas de marcas.
type: docs
weight: 570
url: /es/net/aspose.words.drawing.charts/axisticklabelposition/
---
## AxisTickLabelPosition enumeration

Especifica las posiciones posibles para las etiquetas de marcas.

```csharp
public enum AxisTickLabelPosition
```

### Valores

| Nombre | Valor | Descripción |
| --- | --- | --- |
| High | `0` | Especifica que las etiquetas de los ejes estarán en el extremo superior del eje perpendicular. |
| Low | `1` | Especifica que las etiquetas de los ejes estarán en el extremo inferior del eje perpendicular. |
| NextToAxis | `2` | Especifica que las etiquetas de los ejes estarán al lado del eje. |
| None | `3` | Especifica que las etiquetas de los ejes no se dibujan. |
| Default | `2` | Especifica el valor predeterminado de la posición de las etiquetas de marca. |

### Ejemplos

Muestra cómo insertar un gráfico con valores de fecha/hora.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Line, 500, 300);
Chart chart = shape.Chart;

// Borre la serie de datos de demostración del gráfico para comenzar con un gráfico limpio.
chart.Series.Clear();

// Agregue una serie personalizada que contenga valores de fecha/hora para el eje X y valores decimales respectivos para el eje Y.
chart.Series.Add("Aspose Test Series",
    new[]
    {
        new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
        new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
    },
    new[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });

// Establecer límites inferior y superior para el eje X.
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03));

// Establecer las unidades principales del eje X en una semana y las unidades secundarias en un día.
xAxis.BaseTimeUnit = AxisTimeUnit.Days;
xAxis.MajorUnit = 7.0d;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorUnit = 1.0d;
xAxis.MinorTickMark = AxisTickMark.Outside;

// Definir propiedades del eje Y para valores decimales.
ChartAxis yAxis = chart.AxisY;
yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100.0d;
yAxis.MinorUnit = 50.0d;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);

doc.Save(ArtifactsDir + "Charts.DateTimeValues.docx");
```

### Ver también

* espacio de nombres [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* asamblea [Aspose.Words](../../)


