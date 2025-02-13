---
title: Enum OfficeMathDisplayType
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Math.OfficeMathDisplayType enumeración. Especifica el tipo de formato de visualización de la ecuación.
type: docs
weight: 3890
url: /es/net/aspose.words.math/officemathdisplaytype/
---
## OfficeMathDisplayType enumeration

Especifica el tipo de formato de visualización de la ecuación.

```csharp
public enum OfficeMathDisplayType
```

### Valores

| Nombre | Valor | Descripción |
| --- | --- | --- |
| Display | `0` | Office Math se muestra en su propia línea. |
| Inline | `1` | Office Math se muestra en línea con el texto. |

### Ejemplos

Muestra cómo configurar el formato de visualización de Office Math.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath officeMath = (OfficeMath) doc.GetChild(NodeType.OfficeMath, 0, true);

// Los nodos de OfficeMath que son hijos de otros nodos de OfficeMath siempre están en línea.
// El nodo con el que estamos trabajando es el nodo base para cambiar su ubicación y tipo de visualización.
Assert.AreEqual(MathObjectType.OMathPara, officeMath.MathObjectType);
Assert.AreEqual(NodeType.OfficeMath, officeMath.NodeType);
Assert.AreEqual(officeMath.ParentNode, officeMath.ParentParagraph);

// Los formatos OOXML y WML utilizan la propiedad "EquationXmlEncoding".
Assert.IsNull(officeMath.EquationXmlEncoding);

// Cambiar la ubicación y el tipo de visualización del nodo OfficeMath.
officeMath.DisplayType = OfficeMathDisplayType.Display;
officeMath.Justification = OfficeMathJustification.Left;

doc.Save(ArtifactsDir + "Shape.OfficeMath.docx");
```

### Ver también

* espacio de nombres [Aspose.Words.Math](../../aspose.words.math/)
* asamblea [Aspose.Words](../../)


