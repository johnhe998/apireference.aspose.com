---
title: XmlMapping.PrefixMappings
second_title: Aspose.Words for .NET API Referansı
description: XmlMapping mülk. Değerlendirmek için XML ad alanı önek eşlemelerini döndürür.XPath .
type: docs
weight: 30
url: /tr/net/aspose.words.markup/xmlmapping/prefixmappings/
---
## XmlMapping.PrefixMappings property

Değerlendirmek için XML ad alanı önek eşlemelerini döndürür.[`XPath`](../xpath/) .

```csharp
public string PrefixMappings { get; }
```

### Notlar

XPath ifadesi belgedeki özel XML veri bölümlerine karşı değerlendirildiğinde, XPath ifadesini yorumlamak için kullanılacak önek eşlemeleri kümesini belirtir.

### Örnekler

Özel XML parçaları için XML eşlemelerinin nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();

// Metin içeren bir XML bölümü oluşturun ve bunu belgenin CustomXmlPart koleksiyonuna ekleyin.
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);

Assert.AreEqual("<root><text>Text element #1</text><text>Text element #2</text></root>", 
    Encoding.UTF8.GetString(xmlPart.Data));

// CustomXmlPart'ımızın içeriğini görüntüleyecek yapılandırılmış bir belge etiketi oluşturun.
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);

// Yapılandırılmış belge etiketimiz için bir eşleme ayarlayın. Bu haritalama talimat verecek
// XPath'in işaret ettiği XML bölümünün metin içeriğinin bir bölümünü görüntülemek için yapılandırılmış belge etiketimiz.
// Bu durumda, ikinci "<metin>" içeriği olacaktır. ilk "<root>" öğesi öğe: "Metin öğesi #2".
tag.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", "xmlns:ns='http://www.w3.org/2001/XMLSchema'");

Assert.True(tag.XmlMapping.IsMapped);
Assert.AreEqual(xmlPart, tag.XmlMapping.CustomXmlPart);
Assert.AreEqual("/root[1]/text[2]", tag.XmlMapping.XPath);
Assert.AreEqual("xmlns:ns='http://www.w3.org/2001/XMLSchema'", tag.XmlMapping.PrefixMappings);

// Özel bölümümüzdeki içeriği görüntülemek için yapılandırılmış belge etiketini belgeye ekleyin.
doc.FirstSection.Body.AppendChild(tag);
doc.Save(ArtifactsDir + "StructuredDocumentTag.XmlMapping.docx");
```

### Ayrıca bakınız

* class [XmlMapping](../)
* ad alanı [Aspose.Words.Markup](../../xmlmapping/)
* toplantı [Aspose.Words](../../../)


