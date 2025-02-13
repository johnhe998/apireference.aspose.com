---
title: SaveOptions.DmlRenderingMode
second_title: Referencia de API de Aspose.Words para .NET
description: SaveOptions propiedad. Obtiene o establece un valor que determina cómo se representan las formas de DrawingML.
type: docs
weight: 70
url: /es/net/aspose.words.saving/saveoptions/dmlrenderingmode/
---
## SaveOptions.DmlRenderingMode property

Obtiene o establece un valor que determina cómo se representan las formas de DrawingML.

```csharp
public DmlRenderingMode DmlRenderingMode { get; set; }
```

### Observaciones

El valor predeterminado esFallback .

Esta propiedad se utiliza cuando el documento se exporta a formatos de página fijos.

### Ejemplos

Muestra cómo renderizar formas alternativas al guardar en PDF.

```csharp
Document doc = new Document(MyDir + "DrawingML shape fallbacks.docx");

// Crea un objeto "PdfSaveOptions" que podemos pasar al método "Guardar" del documento
// para modificar cómo ese método convierte el documento a .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Establecer la propiedad "DmlRenderingMode" en "DmlRenderingMode.Fallback"
// para sustituir formas DML con sus formas alternativas.
// Establecer la propiedad "DmlRenderingMode" en "DmlRenderingMode.DrawingML"
// para renderizar las propias formas DML.
options.DmlRenderingMode = dmlRenderingMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.DrawingMLFallback.pdf", options);
```

Muestra cómo configurar la calidad de representación de los efectos DrawingML en un documento mientras lo guardamos en PDF.

```csharp
Document doc = new Document(MyDir + "DrawingML shape effects.docx");

// Crea un objeto "PdfSaveOptions" que podemos pasar al método "Guardar" del documento
// para modificar cómo ese método convierte el documento a .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Establezca la propiedad "DmlEffectsRenderingMode" en "DmlEffectsRenderingMode.None" para descartar todos los efectos de DrawingML.
// Establecer la propiedad "DmlEffectsRenderingMode" en "DmlEffectsRenderingMode.Simplified"
// para renderizar una versión simplificada de los efectos DrawingML.
// Establecer la propiedad "DmlEffectsRenderingMode" en "DmlEffectsRenderingMode.Fine" para
// renderiza los efectos de DrawingML con más precisión y también con un mayor costo de procesamiento.
options.DmlEffectsRenderingMode = effectsRenderingMode;

Assert.AreEqual(DmlRenderingMode.DrawingML, options.DmlRenderingMode);

doc.Save(ArtifactsDir + "PdfSaveOptions.DrawingMLEffects.pdf", options);
```

### Ver también

* enum [DmlRenderingMode](../../dmlrenderingmode/)
* class [SaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../saveoptions/)
* asamblea [Aspose.Words](../../../)


