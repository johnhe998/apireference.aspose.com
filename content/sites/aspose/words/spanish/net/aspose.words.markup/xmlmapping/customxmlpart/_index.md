---
title: XmlMapping.CustomXmlPart
second_title: Referencia de API de Aspose.Words para .NET
description: XmlMapping propiedad. Devuelve la parte de datos XML personalizada a la que se asigna la etiqueta del documento estructurado principal.
type: docs
weight: 10
url: /es/net/aspose.words.markup/xmlmapping/customxmlpart/
---
## XmlMapping.CustomXmlPart property

Devuelve la parte de datos XML personalizada a la que se asigna la etiqueta del documento estructurado principal.

```csharp
public CustomXmlPart CustomXmlPart { get; }
```

### Ejemplos

Muestra cómo establecer asignaciones XML para partes XML personalizadas.

```csharp
Document doc = new Document();

// Construya una parte XML que contenga texto y agréguela a la colección CustomXmlPart del documento.
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);

Assert.AreEqual("<root><text>Text element #1</text><text>Text element #2</text></root>", 
    Encoding.UTF8.GetString(xmlPart.Data));

// Cree una etiqueta de documento estructurado que mostrará el contenido de nuestro CustomXmlPart.
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);

// Establecer una asignación para nuestra etiqueta de documento estructurado. Este mapeo le indicará
// nuestra etiqueta de documento estructurado para mostrar una parte del contenido de texto de la parte XML al que apunta XPath.
// En este caso, será contenido del segundo "<texto>" elemento del primer "<root>" elemento: "Elemento de texto #2".
tag.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", "xmlns:ns='http://www.w3.org/2001/XMLSchema'");

Assert.True(tag.XmlMapping.IsMapped);
Assert.AreEqual(xmlPart, tag.XmlMapping.CustomXmlPart);
Assert.AreEqual("/root[1]/text[2]", tag.XmlMapping.XPath);
Assert.AreEqual("xmlns:ns='http://www.w3.org/2001/XMLSchema'", etiqueta.XmlMapping.PrefixMappings);

// Agregue la etiqueta de documento estructurado al documento para mostrar el contenido de nuestra parte personalizada.
doc.FirstSection.Body.AppendChild(tag);
doc.Save(ArtifactsDir + "StructuredDocumentTag.XmlMapping.docx");
```

### Ver también

* class [CustomXmlPart](../../customxmlpart/)
* class [XmlMapping](../)
* espacio de nombres [Aspose.Words.Markup](../../xmlmapping/)
* asamblea [Aspose.Words](../../../)


