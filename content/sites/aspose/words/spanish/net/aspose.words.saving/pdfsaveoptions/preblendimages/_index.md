---
title: PdfSaveOptions.PreblendImages
second_title: Referencia de API de Aspose.Words para .NET
description: PdfSaveOptions propiedad. Obtiene o establece un valor que determina si se combinan o no las imágenes transparentes con el color de fondo negro.
type: docs
weight: 230
url: /es/net/aspose.words.saving/pdfsaveoptions/preblendimages/
---
## PdfSaveOptions.PreblendImages property

Obtiene o establece un valor que determina si se combinan o no las imágenes transparentes con el color de fondo negro.

```csharp
public bool PreblendImages { get; set; }
```

### Observaciones

La mezcla previa de imágenes puede mejorar la apariencia visual del documento PDF en Adobe Reader y eliminar los artefactos de suavizado.

Para mostrar correctamente las imágenes premezcladas, la aplicación de visor de PDF debe admitir la entrada /Mate en el diccionario de imágenes de máscara suave. Además, la premezcla de imágenes puede disminuir el rendimiento de la representación de PDF.

El valor predeterminado es`falso`.

### Ejemplos

Muestra cómo combinar previamente imágenes con fondos transparentes al guardar un documento en PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Image img = Image.FromFile(ImageDir + "Transparent background logo.png");
builder.InsertImage(img);

// Crea un objeto "PdfSaveOptions" que podemos pasar al método "Guardar" del documento
// para modificar cómo ese método convierte el documento a .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Establecer la propiedad "PreblendImages" en "true" para premezclar imágenes transparentes
// con un fondo, lo que puede reducir los artefactos.
// Establezca la propiedad "PreblendImages" en "falso" para representar imágenes transparentes normalmente.
options.PreblendImages = preblendImages;

doc.Save(ArtifactsDir + "PdfSaveOptions.PreblendImages.pdf", options);
```

Muestra cómo combinar previamente imágenes con fondos transparentes (.NetStandard 2.0).

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (Image image = Image.Decode(ImageDir + "Transparent background logo.png"))
    builder.InsertImage(image);

// Crea un objeto "PdfSaveOptions" que podemos pasar al método "Guardar" del documento
// para modificar cómo ese método convierte el documento a .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Establecer la propiedad "PreblendImages" en "true" para premezclar imágenes transparentes
// con un fondo, lo que puede reducir los artefactos.
// Establezca la propiedad "PreblendImages" en "falso" para representar imágenes transparentes normalmente.
options.PreblendImages = preblendImages;

doc.Save(ArtifactsDir + "PdfSaveOptions.PreblendImagesNetStandard2.pdf", options);
```

### Ver también

* class [PdfSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../pdfsaveoptions/)
* asamblea [Aspose.Words](../../../)


