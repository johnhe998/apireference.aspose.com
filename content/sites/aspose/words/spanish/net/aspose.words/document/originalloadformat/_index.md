---
title: Document.OriginalLoadFormat
second_title: Referencia de API de Aspose.Words para .NET
description: Document propiedad. Obtiene el formato del documento original que se cargó en este objeto.
type: docs
weight: 280
url: /es/net/aspose.words/document/originalloadformat/
---
## Document.OriginalLoadFormat property

Obtiene el formato del documento original que se cargó en este objeto.

```csharp
public LoadFormat OriginalLoadFormat { get; }
```

### Observaciones

Si creó un nuevo documento en blanco, devuelve elDoc valor.

### Ejemplos

Muestra cómo recuperar detalles de la operación de carga de un documento.

```csharp
Document doc = new Document(MyDir + "Document.docx");

Assert.AreEqual(MyDir + "Document.docx", doc.OriginalFileName);
Assert.AreEqual(LoadFormat.Docx, doc.OriginalLoadFormat);
```

### Ver también

* enum [LoadFormat](../../loadformat/)
* class [Document](../)
* espacio de nombres [Aspose.Words](../../document/)
* asamblea [Aspose.Words](../../../)


