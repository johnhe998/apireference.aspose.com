---
title: Watermark.Remove
second_title: Referencia de API de Aspose.Words para .NET
description: Watermark método. Elimina la marca de agua.
type: docs
weight: 20
url: /es/net/aspose.words/watermark/remove/
---
## Watermark.Remove method

Elimina la marca de agua.

```csharp
public void Remove()
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

* class [Watermark](../)
* espacio de nombres [Aspose.Words](../../watermark/)
* asamblea [Aspose.Words](../../../)


