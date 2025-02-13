---
title: OfficeMath.NodeType
second_title: Aspose.Words for .NET API Referansı
description: OfficeMath mülk. İade NodeType.OfficeMath .
type: docs
weight: 50
url: /tr/net/aspose.words.math/officemath/nodetype/
---
## OfficeMath.NodeType property

İade **NodeType.OfficeMath** .

```csharp
public override NodeType NodeType { get; }
```

### Örnekler

Office matematik ekranı biçimlendirmesinin nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath officeMath = (OfficeMath) doc.GetChild(NodeType.OfficeMath, 0, true);

// Diğer OfficeMath düğümlerinin çocukları olan OfficeMath düğümleri her zaman satır içidir.
// Çalıştığımız düğüm, konumunu ve görüntüleme türünü değiştirmek için temel düğümdür.
Assert.AreEqual(MathObjectType.OMathPara, officeMath.MathObjectType);
Assert.AreEqual(NodeType.OfficeMath, officeMath.NodeType);
Assert.AreEqual(officeMath.ParentNode, officeMath.ParentParagraph);

// OOXML ve WML biçimleri "EquationXmlEncoding" özelliğini kullanır.
Assert.IsNull(officeMath.EquationXmlEncoding);

// OfficeMath düğümünün konumunu ve görüntüleme türünü değiştirin.
officeMath.DisplayType = OfficeMathDisplayType.Display;
officeMath.Justification = OfficeMathJustification.Left;

doc.Save(ArtifactsDir + "Shape.OfficeMath.docx");
```

### Ayrıca bakınız

* enum [NodeType](../../../aspose.words/nodetype/)
* class [OfficeMath](../)
* ad alanı [Aspose.Words.Math](../../officemath/)
* toplantı [Aspose.Words](../../../)


