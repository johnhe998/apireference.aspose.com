---
title: Enum EmfPlusDualRenderingMode
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Saving.EmfPlusDualRenderingMode enumeración. Especifica cómo Aspose.Words debe representar los metarchivos EMF Dual.
type: docs
weight: 4720
url: /es/net/aspose.words.saving/emfplusdualrenderingmode/
---
## EmfPlusDualRenderingMode enumeration

Especifica cómo Aspose.Words debe representar los metarchivos EMF+ Dual.

```csharp
public enum EmfPlusDualRenderingMode
```

### Valores

| Nombre | Valor | Descripción |
| --- | --- | --- |
| EmfPlusWithFallback | `0` | Aspose.Words intenta convertir EMF+ en parte del metarchivo EMF+ Dual. Si algunos de los registros EMF+ no son compatibles , Aspose.Words hace que EMF forme parte del metarchivo dual EMF+. |
| EmfPlus | `1` | Aspose.Words hace que EMF+ forme parte del metarchivo dual EMF+. |
| Emf | `2` | Aspose.Words hace que EMF forme parte del metarchivo dual EMF+. |

### Ejemplos

Muestra cómo configurar las opciones de representación relacionadas con el metarchivo mejorado de Windows al guardar en PDF.

```csharp
Document doc = new Document(MyDir + "EMF.docx");

// Crea un objeto "PdfSaveOptions" que podemos pasar al método "Guardar" del documento
// para modificar cómo ese método convierte el documento a .PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Establecer la propiedad "EmfPlusDualRenderingMode" en "EmfPlusDualRenderingMode.Emf"
// para renderizar solo la parte EMF de un metarchivo dual EMF+.
// Establezca la propiedad "EmfPlusDualRenderingMode" en "EmfPlusDualRenderingMode.EmfPlus" para
// para representar la parte EMF+ de un metarchivo dual EMF+.
// Establecer la propiedad "EmfPlusDualRenderingMode" en "EmfPlusDualRenderingMode.EmfPlusWithFallback"
// para representar la parte EMF+ de un metarchivo dual EMF+ si se admiten todos los registros EMF+.
// De lo contrario, Aspose.Words representará la parte EMF.
saveOptions.MetafileRenderingOptions.EmfPlusDualRenderingMode = renderingMode;

// Establezca la propiedad "UseEmfEmbeddedToWmf" en "true" para representar datos EMF incrustados
// para metarchivos que podemos representar como gráficos vectoriales.
saveOptions.MetafileRenderingOptions.UseEmfEmbeddedToWmf = true;

doc.Save(ArtifactsDir + "PdfSaveOptions.RenderMetafile.pdf", saveOptions);
```

### Ver también

* espacio de nombres [Aspose.Words.Saving](../../aspose.words.saving/)
* asamblea [Aspose.Words](../../)


