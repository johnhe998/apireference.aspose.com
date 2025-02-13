---
title: OfficeMath.DisplayType
second_title: Aspose.Words for .NET API Referansı
description: OfficeMath mülk. Bir denklemin metniyle satır içi mi yoksa kendi satırında mı görüntüleneceğini temsil eden Office Math görüntüleme biçimi türünü alır/ayarlar.
type: docs
weight: 10
url: /tr/net/aspose.words.math/officemath/displaytype/
---
## OfficeMath.DisplayType property

Bir denklemin metniyle satır içi mi yoksa kendi satırında mı görüntüleneceğini temsil eden Office Math görüntüleme biçimi türünü alır/ayarlar.

```csharp
public OfficeMathDisplayType DisplayType { get; set; }
```

### Notlar

Görüntüleme biçimi türü yalnızca üst düzey Office Math için etkilidir.

Döndürülen görüntüleme biçimi türü her zamanInline iç içe Office Math için.

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

* enum [OfficeMathDisplayType](../../officemathdisplaytype/)
* class [OfficeMath](../)
* ad alanı [Aspose.Words.Math](../../officemath/)
* toplantı [Aspose.Words](../../../)


