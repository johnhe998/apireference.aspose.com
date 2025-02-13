---
title: XmlMapping.StoreItemId
second_title: Referencia de API de Aspose.Words para .NET
description: XmlMapping propiedad. Especifica el identificador de datos XML personalizados para la parte de datos XML personalizados que se utilizará para evaluar laXPath expresión.
type: docs
weight: 40
url: /es/net/aspose.words.markup/xmlmapping/storeitemid/
---
## XmlMapping.StoreItemId property

Especifica el identificador de datos XML personalizados para la parte de datos XML personalizados que se utilizará para evaluar la[`XPath`](../xpath/) expresión.

```csharp
public string StoreItemId { get; }
```

### Ejemplos

Muestra cómo obtener el identificador de datos XML personalizado de una parte XML.

```csharp
Document doc = new Document(MyDir + "Custom XML part in structured document tag.docx");

// Las etiquetas de documentos estructurados tienen ID en forma de GUID.
StructuredDocumentTag tag = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);

Assert.AreEqual("{F3029283-4FF8-4DD2-9F31-395F19ACEE85}", tag.XmlMapping.StoreItemId);
```

### Ver también

* class [XmlMapping](../)
* espacio de nombres [Aspose.Words.Markup](../../xmlmapping/)
* asamblea [Aspose.Words](../../../)


