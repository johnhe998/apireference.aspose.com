---
title: OfficeMath.Justification
second_title: Aspose.Words für .NET-API-Referenz
description: OfficeMath eigendom. Ruft Office MathAusrichtung ab/legt sie fest.
type: docs
weight: 30
url: /de/net/aspose.words.math/officemath/justification/
---
## OfficeMath.Justification property

Ruft Office Math-Ausrichtung ab/legt sie fest.

```csharp
public OfficeMathJustification Justification { get; set; }
```

### Bemerkungen

Die Ausrichtung kann nicht auf Office Math mit Anzeigeformattyp eingestellt werdenInline.

Die Inline-Ausrichtung kann nicht auf den Formattyp Office Math mit Anzeigeformat festgelegt werdenDisplay.

Dazugehörigen[`DisplayType`](../displaytype/) muss vor dem Festlegen der Office Math-Ausrichtung festgelegt werden.

### Beispiele

Zeigt, wie die Anzeigeformatierung für Office-Mathematik eingestellt wird.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath officeMath = (OfficeMath) doc.GetChild(NodeType.OfficeMath, 0, true);

// OfficeMath-Knoten, die Kinder anderer OfficeMath-Knoten sind, sind immer inline.
// Der Knoten, mit dem wir arbeiten, ist der Basisknoten, um seine Position und seinen Anzeigetyp zu ändern.
Assert.AreEqual(MathObjectType.OMathPara, officeMath.MathObjectType);
Assert.AreEqual(NodeType.OfficeMath, officeMath.NodeType);
Assert.AreEqual(officeMath.ParentNode, officeMath.ParentParagraph);

// OOXML- und WML-Formate verwenden die Eigenschaft "EquationXmlEncoding".
Assert.IsNull(officeMath.EquationXmlEncoding);

// Position und Anzeigetyp des OfficeMath-Knotens ändern.
officeMath.DisplayType = OfficeMathDisplayType.Display;
officeMath.Justification = OfficeMathJustification.Left;

doc.Save(ArtifactsDir + "Shape.OfficeMath.docx");
```

### Siehe auch

* enum [OfficeMathJustification](../../officemathjustification/)
* class [OfficeMath](../)
* namensraum [Aspose.Words.Math](../../officemath/)
* Montage [Aspose.Words](../../../)


