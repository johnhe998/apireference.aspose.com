---
title: AxisDisplayUnit.CustomUnit
second_title: Referencia de API de Aspose.Words para .NET
description: AxisDisplayUnit propiedad. Obtiene o establece un divisor definido por el usuario para escalar las unidades de visualización en el eje de valores.
type: docs
weight: 20
url: /es/net/aspose.words.drawing.charts/axisdisplayunit/customunit/
---
## AxisDisplayUnit.CustomUnit property

Obtiene o establece un divisor definido por el usuario para escalar las unidades de visualización en el eje de valores.

```csharp
public double CustomUnit { get; set; }
```

### Observaciones

La propiedad no es compatible con los nuevos gráficos de MS Office 2016. El valor predeterminado es 1.

Al establecer esta propiedad, se establece el[`Unit`](../unit/) propiedad a Custom.

### Ejemplos

Muestra cómo manipular las marcas de verificación y los valores mostrados de un eje de gráfico.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
Chart chart = shape.Chart;

Assert.AreEqual(1, chart.Series.Count);
Assert.AreEqual("Y-Values", chart.Series[0].Name);

// Establezca las marcas de verificación menores del eje Y para que apunten lejos del área de trazado,
// y las marcas principales para cruzar el eje.
ChartAxis axis = chart.AxisY;
axis.MajorTickMark = AxisTickMark.Cross;
axis.MinorTickMark = AxisTickMark.Outside;

// Establece el eje Y para mostrar un tick mayor cada 10 unidades y un tick menor cada 1 unidad.
axis.MajorUnit = 10;
axis.MinorUnit = 1;

// Establecer los límites del eje Y en -10 y 20.
// Este eje Y ahora mostrará 4 marcas principales y 27 marcas secundarias.
axis.Scaling.Minimum = new AxisBound(-10);
axis.Scaling.Maximum = new AxisBound(20);

// Para el eje X, establezca las marcas principales cada 10 unidades,
// cada marca de verificación menor a 2,5 unidades.
axis = chart.AxisX;
axis.MajorUnit = 10;
axis.MinorUnit = 2.5;

// Configure ambos tipos de marcas de verificación para que aparezcan dentro del área de trazado del gráfico.
axis.MajorTickMark = AxisTickMark.Inside;
axis.MinorTickMark = AxisTickMark.Inside;

// Establecer los límites del eje X para que el eje X abarque 5 marcas principales y 12 marcas secundarias.
axis.Scaling.Minimum = new AxisBound(-10);
axis.Scaling.Maximum = new AxisBound(30);
axis.TickLabelAlignment = ParagraphAlignment.Right;

Assert.AreEqual(1, axis.TickLabelSpacing);

// Establecer las etiquetas de marca para mostrar su valor en millones.
axis.DisplayUnit.Unit = AxisBuiltInUnit.Millions;

// Podemos establecer un valor más específico por el cual las etiquetas de marca mostrarán sus valores.
// Esta declaración es equivalente a la anterior.
axis.DisplayUnit.CustomUnit = 1000000;
doc.Save(ArtifactsDir + "Charts.AxisDisplayUnit.docx");
```

### Ver también

* class [AxisDisplayUnit](../)
* espacio de nombres [Aspose.Words.Drawing.Charts](../../axisdisplayunit/)
* asamblea [Aspose.Words](../../../)


