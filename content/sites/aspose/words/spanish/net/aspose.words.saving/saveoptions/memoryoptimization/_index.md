---
title: SaveOptions.MemoryOptimization
second_title: Referencia de API de Aspose.Words para .NET
description: SaveOptions propiedad. Obtiene o establece el valor que determina si se debe realizar la optimización de la memoria antes de guardar el documento. El valor predeterminado para esta propiedad es falso .
type: docs
weight: 110
url: /es/net/aspose.words.saving/saveoptions/memoryoptimization/
---
## SaveOptions.MemoryOptimization property

Obtiene o establece el valor que determina si se debe realizar la optimización de la memoria antes de guardar el documento. El valor predeterminado para esta propiedad es **falso** .

```csharp
public bool MemoryOptimization { get; set; }
```

### Observaciones

Establecer esta opción en verdadero puede reducir significativamente el consumo de memoria mientras se guardan documentos grandes a costa de un ahorro de tiempo más lento.

### Ejemplos

Muestra una opción para optimizar el consumo de memoria al renderizar documentos grandes a PDF.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Crea un objeto "PdfSaveOptions" que podemos pasar al método "Guardar" del documento
// para modificar cómo ese método convierte el documento a .PDF.
SaveOptions saveOptions = SaveOptions.CreateSaveOptions(SaveFormat.Pdf);

// Establezca la propiedad "MemoryOptimization" en "true" para reducir la huella de memoria de las operaciones de guardado de documentos grandes
// a costa de aumentar la duración de la operación.
// Establezca la propiedad "MemoryOptimization" en "false" para guardar el documento como PDF normalmente.
saveOptions.MemoryOptimization = memoryOptimization;

doc.Save(ArtifactsDir + "PdfSaveOptions.MemoryOptimization.pdf", saveOptions);
```

### Ver también

* class [SaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../saveoptions/)
* asamblea [Aspose.Words](../../../)


