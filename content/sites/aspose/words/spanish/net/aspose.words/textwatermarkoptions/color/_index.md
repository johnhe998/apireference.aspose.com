---
title: TextWatermarkOptions.Color
second_title: Referencia de API de Aspose.Words para .NET
description: TextWatermarkOptions propiedad. Obtiene o establece el color de fuente. El valor predeterminado es Color.Silver.
type: docs
weight: 20
url: /es/net/aspose.words/textwatermarkoptions/color/
---
## TextWatermarkOptions.Color property

Obtiene o establece el color de fuente. El valor predeterminado es Color.Silver.

```csharp
public Color Color { get; set; }
```

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


