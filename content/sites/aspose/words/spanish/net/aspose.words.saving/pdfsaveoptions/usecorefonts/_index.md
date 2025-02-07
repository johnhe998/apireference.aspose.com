---
title: PdfSaveOptions.UseCoreFonts
second_title: Referencia de API de Aspose.Words para .NET
description: PdfSaveOptions propiedad. Obtiene o establece un valor que determina si se sustituyen o no las fuentes TrueType Arial Times New Roman Courier New y Symbol con fuentes principales PDF Type 1.
type: docs
weight: 280
url: /es/net/aspose.words.saving/pdfsaveoptions/usecorefonts/
---
## PdfSaveOptions.UseCoreFonts property

Obtiene o establece un valor que determina si se sustituyen o no las fuentes TrueType Arial, Times New Roman, Courier New y Symbol con fuentes principales PDF Type 1.

```csharp
public bool UseCoreFonts { get; set; }
```

### Observaciones

El valor predeterminado es`falso` . Cuando este valor se establece en`verdadero` Las fuentes Arial, Times New Roman, Courier New y Symbol se reemplazan en el documento PDF con la fuente Type 1 principal correspondiente.

Las fuentes principales de PDF, o sus métricas de fuente y fuentes de sustitución adecuadas, deben estar disponibles para cualquier aplicación de visualización de PDF x000d_.

Esta configuración solo funciona para el texto en codificación ANSI (Windows-1252). El texto que no sea ANSI se escribirá con fuente TrueType incrustada independientemente de esta configuración.

El cumplimiento de PDF/A y PDF/UA requiere que se incrusten todas las fuentes.`falso` el valor se usará automáticamente al guardar en PDF/A y PDF/UA.

Las fuentes principales no son compatibles cuando se guarda en formato PDF 2.0.`falso`el valor se usará automáticamente al guardar en PDF 2.0.

Esta opción tiene una prioridad más alta que[`FontEmbeddingMode`](../fontembeddingmode/) opción.

### Ejemplos

Muestra cómo habilitar/deshabilitar la sustitución de fuentes PDF Tipo 1.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Courier New";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

// Crea un objeto "PdfSaveOptions" que podemos pasar al método "Guardar" del documento
// para modificar cómo ese método convierte el documento a .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Establecer la propiedad "UseCoreFonts" en "true" para reemplazar algunas fuentes,
// incluyendo las dos fuentes de nuestro documento, con sus equivalentes en PDF Tipo 1.
// Establezca la propiedad "UseCoreFonts" en "false" para no aplicar fuentes PDF Type 1.
options.UseCoreFonts = useCoreFonts;

doc.Save(ArtifactsDir + "PdfSaveOptions.EmbedCoreFonts.pdf", options);

if (useCoreFonts)
    Assert.That(3000, Is.AtLeast(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedCoreFonts.pdf").Length));
else
    Assert.That(30000, Is.LessThan(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedCoreFonts.pdf").Length));
```

### Ver también

* class [PdfSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../pdfsaveoptions/)
* asamblea [Aspose.Words](../../../)


