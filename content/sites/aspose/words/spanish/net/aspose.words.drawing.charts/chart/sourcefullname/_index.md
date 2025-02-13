---
title: Chart.SourceFullName
second_title: Referencia de API de Aspose.Words para .NET
description: Chart propiedad. Obtiene la ruta y el nombre de un archivo xls/xlsx al que está vinculado este gráfico.
type: docs
weight: 60
url: /es/net/aspose.words.drawing.charts/chart/sourcefullname/
---
## Chart.SourceFullName property

Obtiene la ruta y el nombre de un archivo xls/xlsx al que está vinculado este gráfico.

```csharp
public string SourceFullName { get; set; }
```

### Ejemplos

Muestra cómo obtener el nombre completo del documento xls/xlsx externo si el gráfico está vinculado.

```csharp
Document doc = new Document(MyDir + "Shape with linked chart.docx");

Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);

Assert.True(shape.Chart.SourceFullName.Contains("Examples\\Data\\Spreadsheet.xlsx"));
```

### Ver también

* class [Chart](../)
* espacio de nombres [Aspose.Words.Drawing.Charts](../../chart/)
* asamblea [Aspose.Words](../../../)


