---
title: TextWatermarkOptions.FontSize
second_title: Referencia de API de Aspose.Words para .NET
description: TextWatermarkOptions propiedad. Obtiene o establece un tamaño de fuente. El valor predeterminado es 0  auto.
type: docs
weight: 40
url: /es/net/aspose.words/textwatermarkoptions/fontsize/
---
## TextWatermarkOptions.FontSize property

Obtiene o establece un tamaño de fuente. El valor predeterminado es 0 - auto.

```csharp
public float FontSize { get; set; }
```

### Excepciones

| excepción | condición |
| --- | --- |
| ArgumentOutOfRangeException | Se lanza cuando el argumento estaba fuera del rango de valores válidos. |

### Observaciones

Los valores válidos oscilan entre 0 y 65,5 inclusive.

El tamaño de fuente automático significa que la marca de agua se escalará a su ancho máximo y alto máximo en relación con los márgenes de la página.

### Ejemplos

Muestra cómo crear una marca de agua de texto.

```csharp
Document doc = new Document();

// Agregue una marca de agua de texto sin formato.
doc.Watermark.SetText("Aspose Watermark");

// Si deseamos editar el formato del texto usándolo como marca de agua,
// podemos hacerlo pasando un objeto TextWatermarkOptions al crear la marca de agua.
TextWatermarkOptions textWatermarkOptions = new TextWatermarkOptions();
textWatermarkOptions.FontFamily = "Arial";
textWatermarkOptions.FontSize = 36;
textWatermarkOptions.Color = Color.Black;
textWatermarkOptions.Layout = WatermarkLayout.Diagonal;
textWatermarkOptions.IsSemitrasparent = false;

doc.Watermark.SetText("Aspose Watermark", textWatermarkOptions);

doc.Save(ArtifactsDir + "Document.TextWatermark.docx");

// Podemos eliminar una marca de agua de un documento como este.
if (doc.Watermark.Type == WatermarkType.Text)
    doc.Watermark.Remove();
```

### Ver también

* class [TextWatermarkOptions](../)
* espacio de nombres [Aspose.Words](../../textwatermarkoptions/)
* asamblea [Aspose.Words](../../../)


