---
title: FileFormatInfo.Encoding
second_title: Referencia de API de Aspose.Words para .NET
description: FileFormatInfo propiedad. Obtiene la codificación detectada si corresponde al formato del documento actual. Por el momento detecta la codificación solo para documentos HTML.
type: docs
weight: 10
url: /es/net/aspose.words/fileformatinfo/encoding/
---
## FileFormatInfo.Encoding property

Obtiene la codificación detectada si corresponde al formato del documento actual. Por el momento detecta la codificación solo para documentos HTML.

```csharp
public Encoding Encoding { get; }
```

### Ejemplos

Muestra cómo detectar la codificación en un archivo html.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(MyDir + "Document.html");

Assert.AreEqual(LoadFormat.Html, info.LoadFormat);

// La propiedad Encoding se usa solo cuando creamos un objeto FileFormatInfo para un documento html.
Assert.AreEqual("Western European (Windows)", info.Encoding.EncodingName);
Assert.AreEqual(1252, info.Encoding.CodePage);
```

### Ver también

* class [FileFormatInfo](../)
* espacio de nombres [Aspose.Words](../../fileformatinfo/)
* asamblea [Aspose.Words](../../../)


