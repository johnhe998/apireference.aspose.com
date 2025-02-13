---
title: LayoutOptions.IgnorePrinterMetrics
second_title: Referencia de API de Aspose.Words para .NET
description: LayoutOptions propiedad. Obtiene o establece una indicación de si se ignora la opción de compatibilidad Usar métricas de impresora para diseñar el documento. El valor predeterminado es Verdadero.
type: docs
weight: 50
url: /es/net/aspose.words.layout/layoutoptions/ignoreprintermetrics/
---
## LayoutOptions.IgnorePrinterMetrics property

Obtiene o establece una indicación de si se ignora la opción de compatibilidad "Usar métricas de impresora para diseñar el documento". El valor predeterminado es Verdadero.

```csharp
public bool IgnorePrinterMetrics { get; set; }
```

### Ejemplos

Muestra cómo ignorar la opción 'Usar métricas de impresora para diseñar el documento'.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

doc.LayoutOptions.IgnorePrinterMetrics = false;

doc.Save(ArtifactsDir + "Document.IgnorePrinterMetrics.docx");
```

### Ver también

* class [LayoutOptions](../)
* espacio de nombres [Aspose.Words.Layout](../../layoutoptions/)
* asamblea [Aspose.Words](../../../)


