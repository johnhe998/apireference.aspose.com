---
title: MetafileRenderingOptions.UseEmfEmbeddedToWmf
second_title: Referencia de API de Aspose.Words para .NET
description: MetafileRenderingOptions propiedad. Obtiene o establece un valor que determina cómo se deben representar los metarchivos WMF con metarchivos EMF incrustados.
type: docs
weight: 60
url: /es/net/aspose.words.saving/metafilerenderingoptions/useemfembeddedtowmf/
---
## MetafileRenderingOptions.UseEmfEmbeddedToWmf property

Obtiene o establece un valor que determina cómo se deben representar los metarchivos WMF con metarchivos EMF incrustados.

```csharp
public bool UseEmfEmbeddedToWmf { get; set; }
```

### Observaciones

Los metarchivos WMF podrían contener datos EMF incrustados. En la mayoría de los casos, MS Word usa datos EMF incrustados. GDI+ siempre usa datos WMF.

Cuando este valor se establece en`verdadero`, Aspose.Words utiliza datos EMF incrustados al renderizar.

Cuando este valor se establece en`falso`, Aspose.Words usa datos WMF al renderizar.

Esta opción se usa solo cuando el metarchivo se representa como gráficos vectoriales. Cuando el metarchivo se representa en mapa de bits, siempre se utilizan datos WMF.

El valor predeterminado es`verdadero`.

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

* class [MetafileRenderingOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../metafilerenderingoptions/)
* asamblea [Aspose.Words](../../../)


