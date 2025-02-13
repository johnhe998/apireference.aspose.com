---
title: Enum DmlEffectsRenderingMode
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Saving.DmlEffectsRenderingMode enumeración. Especifica cómo se representan los efectos de DrawingML en formatos de página fijos.
type: docs
weight: 4650
url: /es/net/aspose.words.saving/dmleffectsrenderingmode/
---
## DmlEffectsRenderingMode enumeration

Especifica cómo se representan los efectos de DrawingML en formatos de página fijos.

```csharp
public enum DmlEffectsRenderingMode
```

### Valores

| Nombre | Valor | Descripción |
| --- | --- | --- |
| Simplified | `0` | Se simplifica la representación de los efectos de DrawingML. |
| None | `1` | No se renderizan efectos DrawingML. |
| Fine | `2` | Los efectos de DrawingML se representan en modo fino, lo que implica un procesamiento avanzado. En este modo, la representación de efectos ofrece mejores resultados pero a un costo de rendimiento másSimplified modo. |

### Ejemplos

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


