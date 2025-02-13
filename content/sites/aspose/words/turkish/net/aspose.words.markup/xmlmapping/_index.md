---
title: Class XmlMapping
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Markup.XmlMapping sınıf. parent yapılandırılmış belge etiketi ile belgedeki özel bir XML veri bölümünde depolanan bir XML öğesi arasında bir eşleme oluşturmak için kullanılan bilgileri belirtir.
type: docs
weight: 3860
url: /tr/net/aspose.words.markup/xmlmapping/
---
## XmlMapping class

parent yapılandırılmış belge etiketi ile belgedeki özel bir XML veri bölümünde depolanan bir XML öğesi arasında bir eşleme oluşturmak için kullanılan bilgileri belirtir.

```csharp
public class XmlMapping
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [CustomXmlPart](../../aspose.words.markup/xmlmapping/customxmlpart/) { get; } | Üst yapılandırılmış belge etiketinin eşlendiği özel XML veri bölümünü döndürür. |
| [IsMapped](../../aspose.words.markup/xmlmapping/ismapped/) { get; } | İade **doğru** ana yapılandırılmış belge etiketi başarıyla XML verilerine eşlenirse. |
| [PrefixMappings](../../aspose.words.markup/xmlmapping/prefixmappings/) { get; } | Değerlendirmek için XML ad alanı önek eşlemelerini döndürür.[`XPath`](./xpath/) . |
| [StoreItemId](../../aspose.words.markup/xmlmapping/storeitemid/) { get; } | Özel XML veri bölümü için özel XML veri tanımlayıcısını belirtir ve bu, öğesinin aşağıdakileri değerlendirmek için kullanılacaktır.[`XPath`](./xpath/) ifade. |
| [XPath](../../aspose.words.markup/xmlmapping/xpath/) { get; } | Üst yapılandırılmış belge etiketiyle eşlenen özel XML düğümünü bulmak için değerlendirilen XPath ifadesini döndürür. |

## yöntemler

| İsim | Tanım |
| --- | --- |
| [Delete](../../aspose.words.markup/xmlmapping/delete/)() | Üst yapılandırılmış belgenin XML verileriyle eşlenmesini siler. |
| [SetMapping](../../aspose.words.markup/xmlmapping/setmapping/)(CustomXmlPart, string, string) | Üst yapılandırılmış belge etiketi ile özel bir XML veri bölümünün XML düğümü arasında bir eşleme ayarlar. |

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

* ad alanı [Aspose.Words.Markup](../../aspose.words.markup/)
* toplantı [Aspose.Words](../../)


