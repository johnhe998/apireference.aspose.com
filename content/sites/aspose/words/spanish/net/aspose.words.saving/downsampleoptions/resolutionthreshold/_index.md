---
title: DownsampleOptions.ResolutionThreshold
second_title: Referencia de API de Aspose.Words para .NET
description: DownsampleOptions propiedad. Especifica la resolución de umbral en píxeles por pulgada. Si la resolución de una imagen en el documento es inferior al valor de umbral no se aplicará el algoritmo de reducción de resolución. Un valor de 0 significa que no se utiliza la verificación de umbral y todas las imágenes que se puede reducir el tamaño se reducen.
type: docs
weight: 40
url: /es/net/aspose.words.saving/downsampleoptions/resolutionthreshold/
---
## DownsampleOptions.ResolutionThreshold property

Especifica la resolución de umbral en píxeles por pulgada. Si la resolución de una imagen en el documento es inferior al valor de umbral, no se aplicará el algoritmo de reducción de resolución. Un valor de 0 significa que no se utiliza la verificación de umbral y todas las imágenes que se puede reducir el tamaño se reducen.

```csharp
public int ResolutionThreshold { get; set; }
```

### Observaciones

El valor predeterminado es 0.

### Ejemplos

Muestra cómo cambiar la resolución de las imágenes en el documento PDF.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// Crea un objeto "PdfSaveOptions" que podemos pasar al método "Guardar" del documento
// para modificar cómo ese método convierte el documento a .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Por defecto, Aspose.Words reduce la resolución de todas las imágenes en un documento que guardamos en PDF a 220 ppp.
Assert.True(options.DownsampleOptions.DownsampleImages);
Assert.AreEqual(220, options.DownsampleOptions.Resolution);
Assert.AreEqual(0, options.DownsampleOptions.ResolutionThreshold);

doc.Save(ArtifactsDir + "PdfSaveOptions.DownsampleOptions.Default.pdf", options);

// Establezca la propiedad "Resolución" en "36" para reducir la resolución de todas las imágenes a 36 ppp.
options.DownsampleOptions.Resolution = 36;

// Establecer la propiedad "ResolutionThreshold" para aplicar solo la reducción de resolución a
// imágenes con una resolución superior a 128 ppi.
options.DownsampleOptions.ResolutionThreshold = 128;

// Solo las dos primeras imágenes del documento se reducirán en esta etapa.
doc.Save(ArtifactsDir + "PdfSaveOptions.DownsampleOptions.LowerResolution.pdf", options);
```

### Ver también

* class [DownsampleOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../downsampleoptions/)
* asamblea [Aspose.Words](../../../)


