---
title: OfficeMath.Justification
second_title: Referencia de API de Aspose.Words para .NET
description: OfficeMath propiedad. Obtiene/establece la justificación matemática de Office.
type: docs
weight: 30
url: /es/net/aspose.words.math/officemath/justification/
---
## OfficeMath.Justification property

Obtiene/establece la justificación matemática de Office.

```csharp
public OfficeMathJustification Justification { get; set; }
```

### Observaciones

La justificación no se puede establecer en Office Math con el tipo de formato de visualizaciónInline.

La justificación en línea no se puede establecer en Office Math con el tipo de formato de visualizaciónDisplay.

Correspondiente[`DisplayType`](../displaytype/) debe configurarse antes de configurar la justificación matemática de Office.

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

* enum [OfficeMathJustification](../../officemathjustification/)
* class [OfficeMath](../)
* espacio de nombres [Aspose.Words.Math](../../officemath/)
* asamblea [Aspose.Words](../../../)


