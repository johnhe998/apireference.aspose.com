---
title: StructuredDocumentTagRangeStart.XmlMapping
second_title: Referencia de API de Aspose.Words para .NET
description: StructuredDocumentTagRangeStart propiedad. Obtiene un objeto que representa la asignación de este rango de etiquetas de documento estructurado a datos XML en una parte XML personalizada del documento actual.
type: docs
weight: 180
url: /es/net/aspose.words.markup/structureddocumenttagrangestart/xmlmapping/
---
## StructuredDocumentTagRangeStart.XmlMapping property

Obtiene un objeto que representa la asignación de este rango de etiquetas de documento estructurado a datos XML en una parte XML personalizada del documento actual.

```csharp
public XmlMapping XmlMapping { get; }
```

### Observaciones

Puedes usar el[`SetMapping`](../../xmlmapping/setmapping/) método de este objeto para asignar un rango de etiqueta de documento estructurado a datos XML.

### Ejemplos

Muestra cómo establecer asignaciones XML para el inicio del rango de una etiqueta de documento estructurado.

```csharp
Document doc = new Document(MyDir + "Multi-section structured document tags.docx");

// Construya una parte XML que contenga texto y agréguela a la colección CustomXmlPart del documento.
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);

Assert.AreEqual("<root><text>Text element #1</text><text>Text element #2</text></root>",
    Encoding.UTF8.GetString(xmlPart.Data));

// Cree una etiqueta de documento estructurado que mostrará el contenido de nuestro CustomXmlPart en el documento.
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);

// Si establecemos un mapeo para nuestra etiqueta de documento estructurado,
// solo mostrará una parte de CustomXmlPart a la que apunta XPath.
// Este XPath apuntará al segundo contenido "<text>" elemento del primer "<root>" elemento de nuestro CustomXmlPart.
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);

doc.Save(ArtifactsDir + "StructuredDocumentTag.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### Ver también

* class [XmlMapping](../../xmlmapping/)
* class [StructuredDocumentTagRangeStart](../)
* espacio de nombres [Aspose.Words.Markup](../../structureddocumenttagrangestart/)
* asamblea [Aspose.Words](../../../)


