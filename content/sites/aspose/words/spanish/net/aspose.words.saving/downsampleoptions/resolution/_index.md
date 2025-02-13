---
title: DownsampleOptions.Resolution
second_title: Referencia de API de Aspose.Words para .NET
description: DownsampleOptions propiedad. Especifica la resolución en píxeles por pulgada a la que deben reducirse las muestras de las imágenes.
type: docs
weight: 30
url: /es/net/aspose.words.saving/downsampleoptions/resolution/
---
## DownsampleOptions.Resolution property

Especifica la resolución en píxeles por pulgada a la que deben reducirse las muestras de las imágenes.

```csharp
public int Resolution { get; set; }
```

### Observaciones

El valor predeterminado es 220 ppp.

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


