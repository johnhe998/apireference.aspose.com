---
title: Class Chart
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Drawing.Charts.Chart clase. Proporciona acceso a las propiedades de la forma del gráfico.
type: docs
weight: 600
url: /es/net/aspose.words.drawing.charts/chart/
---
## Chart class

Proporciona acceso a las propiedades de la forma del gráfico.

```csharp
public class Chart
```

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [AxisX](../../aspose.words.drawing.charts/chart/axisx/) { get; } | Proporciona acceso a las propiedades del eje X del gráfico. |
| [AxisY](../../aspose.words.drawing.charts/chart/axisy/) { get; } | Proporciona acceso a las propiedades del eje Y del gráfico. |
| [AxisZ](../../aspose.words.drawing.charts/chart/axisz/) { get; } | Proporciona acceso a las propiedades del eje Z del gráfico. |
| [Legend](../../aspose.words.drawing.charts/chart/legend/) { get; } | Proporciona acceso a las propiedades de la leyenda del gráfico. |
| [Series](../../aspose.words.drawing.charts/chart/series/) { get; } | Proporciona acceso a la colección de series. |
| [SourceFullName](../../aspose.words.drawing.charts/chart/sourcefullname/) { get; set; } | Obtiene la ruta y el nombre de un archivo xls/xlsx al que está vinculado este gráfico. |
| [Title](../../aspose.words.drawing.charts/chart/title/) { get; } | Proporciona acceso a las propiedades del título del gráfico. |

### Ejemplos

Muestra cómo insertar un gráfico y establecer un título.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserte una forma de gráfico con un generador de documentos y obtenga su gráfico.
Shape chartShape = builder.InsertChart(ChartType.Bar, 400, 300);
Chart chart = chartShape.Chart;

// Use la propiedad "Título" para darle un título a nuestro gráfico, que aparece en la parte superior central del área del gráfico.
ChartTitle title = chart.Title;
title.Text = "My Chart";

  // Establezca la propiedad "Mostrar" en "verdadero" para que el título sea visible.
title.Show = true;

// Establezca la propiedad "Superposición" en "verdadero" Dé más espacio a otros elementos del gráfico permitiéndoles superponerse al título
title.Overlay = true;

doc.Save(ArtifactsDir + "Charts.ChartTitle.docx");
```

### Ver también

* espacio de nombres [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* asamblea [Aspose.Words](../../)


