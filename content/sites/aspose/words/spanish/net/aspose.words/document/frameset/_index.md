---
title: Document.Frameset
second_title: Referencia de API de Aspose.Words para .NET
description: Document propiedad. Devuelve unFramesetinstancia si este documento representa una página de marcos.
type: docs
weight: 160
url: /es/net/aspose.words/document/frameset/
---
## Document.Frameset property

Devuelve un`Frameset`instancia si este documento representa una página de marcos.

```csharp
public Frameset Frameset { get; }
```

### Observaciones

Si el documento no está enmarcado, la propiedad tiene la **nulo** valor.

### Ejemplos

Muestra cómo acceder a los marcos en la página.

```csharp
// El documento contiene varios marcos con enlaces a otros documentos.
Document doc = new Document(MyDir + "Frameset.docx");

// Podemos verificar la URL predeterminada (una URL de página web o un documento local) o si el marco es un recurso externo.
Assert.AreEqual("https://file-examples-com.github.io/uploads/2017/02/file-sample_100kB.docx",
    doc.Frameset.ChildFramesets[0].ChildFramesets[0].FrameDefaultUrl);
Assert.True(doc.Frameset.ChildFramesets[0].ChildFramesets[0].IsFrameLinkToFile);

Assert.AreEqual("Document.docx", doc.Frameset.ChildFramesets[1].FrameDefaultUrl);
Assert.False(doc.Frameset.ChildFramesets[1].IsFrameLinkToFile);

// Cambia las propiedades de uno de nuestros marcos.
doc.Frameset.ChildFramesets[0].ChildFramesets[0].FrameDefaultUrl =
    "https://github.com/aspose-words/Aspose.Words-for-.NET/blob/master/Examples/Data/Absolute%20position%20tab.docx";
doc.Frameset.ChildFramesets[0].ChildFramesets[0].IsFrameLinkToFile = false;
```

### Ver también

* class [Frameset](../../../aspose.words.framesets/frameset/)
* class [Document](../)
* espacio de nombres [Aspose.Words](../../document/)
* asamblea [Aspose.Words](../../../)


