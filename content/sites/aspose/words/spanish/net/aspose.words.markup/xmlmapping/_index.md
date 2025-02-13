---
title: Class XmlMapping
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Markup.XmlMapping clase. Especifica la información que se utiliza para establecer una asignación entre la etiqueta del documento estructurado principal y un elemento XML almacenado en una parte de datos XML personalizada en el documento.
type: docs
weight: 3860
url: /es/net/aspose.words.markup/xmlmapping/
---
## XmlMapping class

Especifica la información que se utiliza para establecer una asignación entre la etiqueta del documento estructurado principal y un elemento XML almacenado en una parte de datos XML personalizada en el documento.

```csharp
public class XmlMapping
```

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [CustomXmlPart](../../aspose.words.markup/xmlmapping/customxmlpart/) { get; } | Devuelve la parte de datos XML personalizada a la que se asigna la etiqueta del documento estructurado principal. |
| [IsMapped](../../aspose.words.markup/xmlmapping/ismapped/) { get; } | Devoluciones **verdadero** si la etiqueta del documento estructurado principal se asigna correctamente a datos XML. |
| [PrefixMappings](../../aspose.words.markup/xmlmapping/prefixmappings/) { get; } | Devuelve asignaciones de prefijos de espacios de nombres XML para evaluar el[`XPath`](./xpath/) . |
| [StoreItemId](../../aspose.words.markup/xmlmapping/storeitemid/) { get; } | Especifica el identificador de datos XML personalizados para la parte de datos XML personalizados que se utilizará para evaluar la[`XPath`](./xpath/) expresión. |
| [XPath](../../aspose.words.markup/xmlmapping/xpath/) { get; } | Devuelve la expresión XPath, que se evalúa para encontrar el nodo XML personalizado que está asignado a la etiqueta del documento estructurado principal. |

## Métodos

| Nombre | Descripción |
| --- | --- |
| [Delete](../../aspose.words.markup/xmlmapping/delete/)() | Elimina la asignación del documento estructurado principal a datos XML. |
| [SetMapping](../../aspose.words.markup/xmlmapping/setmapping/)(CustomXmlPart, string, string) | Establece una asignación entre la etiqueta principal del documento estructurado y un nodo XML de una parte de datos XML personalizada. |

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

* espacio de nombres [Aspose.Words.Markup](../../aspose.words.markup/)
* asamblea [Aspose.Words](../../)


