---
title: OfficeMath.ParentParagraph
second_title: Aspose.Words för .NET API Referens
description: OfficeMath fast egendom. Hämtar föräldernParagraph av denna nod.
type: docs
weight: 60
url: /sv/net/aspose.words.math/officemath/parentparagraph/
---
## OfficeMath.ParentParagraph property

Hämtar föräldern[`Paragraph`](../../../aspose.words/paragraph/) av denna nod.

```csharp
public Paragraph ParentParagraph { get; }
```

### Exempel

Visar hur du ställer in kontorsmattevisningsformatering.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath officeMath = (OfficeMath) doc.GetChild(NodeType.OfficeMath, 0, true);

// OfficeMath-noder som är barn till andra OfficeMath-noder är alltid inline.
// Noden vi arbetar med är basnoden för att ändra dess plats och visningstyp.
Assert.AreEqual(MathObjectType.OMathPara, officeMath.MathObjectType);
Assert.AreEqual(NodeType.OfficeMath, officeMath.NodeType);
Assert.AreEqual(officeMath.ParentNode, officeMath.ParentParagraph);

// OOXML- och WML-format använder egenskapen "EquationXmlEncoding".
Assert.IsNull(officeMath.EquationXmlEncoding);

// Ändra plats och visningstyp för OfficeMath-noden.
officeMath.DisplayType = OfficeMathDisplayType.Display;
officeMath.Justification = OfficeMathJustification.Left;

doc.Save(ArtifactsDir + "Shape.OfficeMath.docx");
```

### Se även

* class [Paragraph](../../../aspose.words/paragraph/)
* class [OfficeMath](../)
* namnutrymme [Aspose.Words.Math](../../officemath/)
* hopsättning [Aspose.Words](../../../)


