---
title: Enum DmlRenderingMode
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Saving.DmlRenderingMode enumeración. Especifica cómo se representan las formas de DrawingML en formatos de página fijos.
type: docs
weight: 4660
url: /es/net/aspose.words.saving/dmlrenderingmode/
---
## DmlRenderingMode enumeration

Especifica cómo se representan las formas de DrawingML en formatos de página fijos.

```csharp
public enum DmlRenderingMode
```

### Valores

| Nombre | Valor | Descripción |
| --- | --- | --- |
| Fallback | `0` | Si la forma alternativa está disponible para DrawingML, Aspose.Words representa la forma alternativa en lugar de DrawingML. |
| DrawingML | `1` | Aspose.Words ignora la forma alternativa de DrawingML y representa DrawingML en sí mismo. Este es el modo predeterminado. |

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

* espacio de nombres [Aspose.Words.Saving](../../aspose.words.saving/)
* asamblea [Aspose.Words](../../)


