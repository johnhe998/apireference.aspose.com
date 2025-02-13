---
title: Enum PdfCompliance
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Saving.PdfCompliance enumeración. Especifica el nivel de cumplimiento de estándares de PDF.
type: docs
weight: 5130
url: /es/net/aspose.words.saving/pdfcompliance/
---
## PdfCompliance enumeration

Especifica el nivel de cumplimiento de estándares de PDF.

```csharp
public enum PdfCompliance
```

### Valores

| Nombre | Valor | Descripción |
| --- | --- | --- |
| Pdf17 | `0` | El archivo de salida cumplirá con el estándar PDF 1.7 (ISO 32000-1). |
| Pdf20 | `1` | El archivo de salida cumplirá con el estándar PDF 2.0 (ISO 32000-2). |
| PdfA1a | `2` | El archivo de salida cumplirá con el estándar PDF/A-1a (ISO 19005-1). Este nivel incluye todos los requisitos de PDF/A-1b y además requiere que se incluya la estructura del documento (también conocido como "etiquetado" ), con el objetivo de garantizar que el contenido del documento se pueda buscar y reutilizar. |
| PdfA1b | `3` | El archivo de salida cumplirá con el estándar PDF/A-1b (ISO 19005-1). PDF/A-1b tiene como objetivo garantizar una reproducción fiable de la apariencia visual del documento. |
| PdfA2a | `4` | El archivo de salida cumplirá con el estándar PDF/A-2a (ISO 19005-2). Este nivel incluye todos los requisitos de PDF/A-2u y además requiere que se incluya la estructura del documento (también conocido como "etiquetado" ), con el objetivo de garantizar que el contenido del documento se pueda buscar y reutilizar. |
| PdfA2u | `5` | El archivo de salida cumplirá con el estándar PDF/A-2u (ISO 19005-2). PDF/A-2u tiene como objetivo preservar la apariencia visual estática del documento a lo largo del tiempo, independientemente de las herramientas y los sistemas utilizados para crear, almacenar o renderizar los archivos. Además, cualquier texto contenido en el documento se puede extraer de forma fiable como una serie de puntos de código Unicode. |
| PdfA4 | `6` | El archivo de salida cumplirá con el estándar PDF/A-4 (ISO 19005-4:2020). PDF/A-4 tiene el objetivo de preservar la apariencia visual estática del documento a lo largo del tiempo, independientemente de las herramientas y los sistemas utilizados para crear , almacenar o renderizar los archivos. Además, cualquier texto contenido en el documento se puede extraer de forma fiable como una serie de puntos de código Unicode. |
| PdfUa1 | `7` | El archivo de salida cumplirá con el estándar PDF/UA-1 (ISO 14289-1). El propósito principal de PDF/UA es definir cómo representar documentos electrónicos en formato PDF de una manera que permita que el archivo sea accesible. |

### Ejemplos

Muestra cómo establecer el nivel de cumplimiento de los estándares PDF de los documentos PDF guardados.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// Crea un objeto "PdfSaveOptions" que podemos pasar al método "Guardar" del documento
// para modificar cómo ese método convierte el documento a .PDF.
// Tenga en cuenta que algunas PdfSaveOptions están prohibidas al guardar en uno de los estándares y se corrigen automáticamente.
// Use IWarningCallback para saber qué opciones se corrigen automáticamente.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Establezca la propiedad "Cumplimiento" en "PdfCompliance.PdfA1b" para cumplir con el estándar "PDF/A-1b",
// que tiene como objetivo preservar la apariencia visual del documento ya que Aspose.Words lo convierte a PDF.
// Establezca la propiedad "Cumplimiento" en "PdfCompliance.Pdf17" para cumplir con el estándar "1.7".
// Establezca la propiedad "Cumplimiento" en "PdfCompliance.PdfA1a" para cumplir con el estándar "PDF/A-1a",
// que cumple con "PDF/A-1b" y conserva la estructura del documento original.
// Establezca la propiedad "Cumplimiento" en "PdfCompliance.PdfUa1" para cumplir con el estándar "PDF/UA-1" (ISO 14289-1),
// que tiene como objetivo definir representar documentos electrónicos en PDF que permitan que el archivo sea accesible.
// Esto ayuda a que los documentos se puedan buscar, pero puede aumentar significativamente el tamaño de los documentos que ya son grandes.
saveOptions.Compliance = pdfCompliance;

doc.Save(ArtifactsDir + "PdfSaveOptions.Compliance.pdf", saveOptions);
```

### Ver también

* espacio de nombres [Aspose.Words.Saving](../../aspose.words.saving/)
* asamblea [Aspose.Words](../../)


