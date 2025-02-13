---
title: OleFormat.ProgId
second_title: Referencia de API de Aspose.Words para .NET
description: OleFormat propiedad. Obtiene o establece el ProgID del objeto OLE.
type: docs
weight: 90
url: /es/net/aspose.words.drawing/oleformat/progid/
---
## OleFormat.ProgId property

Obtiene o establece el ProgID del objeto OLE.

```csharp
public string ProgId { get; set; }
```

### Observaciones

La propiedad ProgID no siempre está presente en los documentos de Microsoft Word y no se puede confiar en ella.

No puede ser nulo.

El valor predeterminado es una cadena vacía.

### Ejemplos

Muestra cómo extraer objetos OLE incrustados en archivos.

```csharp
Document doc = new Document(MyDir + "OLE spreadsheet.docm");
Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);

// El objeto OLE de la primera forma es una hoja de cálculo de Microsoft Excel.
OleFormat oleFormat = shape.OleFormat;

Assert.AreEqual("Excel.Sheet.12", oleFormat.ProgId);

// Nuestro objeto no se actualiza automáticamente ni está bloqueado para actualizaciones.
Assert.False(oleFormat.AutoUpdate);
Assert.AreEqual(false, oleFormat.IsLocked);

// Si planeamos guardar el objeto OLE en un archivo en el sistema de archivos local,
// podemos usar la propiedad "SuggestedExtension" para determinar qué extensión de archivo aplicar al archivo.
Assert.AreEqual(".xlsx", oleFormat.SuggestedExtension);

// A continuación se muestran dos formas de guardar un objeto OLE en un archivo en el sistema de archivos local.
// 1 - Guárdelo a través de una transmisión:
using (FileStream fs = new FileStream(ArtifactsDir + "OLE spreadsheet extracted via stream" + oleFormat.SuggestedExtension, FileMode.Create))
{
    oleFormat.Save(fs);
}

// 2 - Guardarlo directamente en un nombre de archivo:
oleFormat.Save(ArtifactsDir + "OLE spreadsheet saved directly" + oleFormat.SuggestedExtension);
```

### Ver también

* class [OleFormat](../)
* espacio de nombres [Aspose.Words.Drawing](../../oleformat/)
* asamblea [Aspose.Words](../../../)


