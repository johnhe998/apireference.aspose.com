---
title: CustomXmlPart.DataChecksum
second_title: Aspose.Words for .NET API Referansı
description: CustomXmlPart mülk. Döngüsel artıklık denetimi CRC sağlama toplamını belirtir.Data içerik.
type: docs
weight: 30
url: /tr/net/aspose.words.markup/customxmlpart/datachecksum/
---
## CustomXmlPart.DataChecksum property

Döngüsel artıklık denetimi (CRC) sağlama toplamını belirtir.[`Data`](../data/) içerik.

```csharp
public long DataChecksum { get; }
```

### Örnekler

Bir çalışma zamanında sağlama toplamının nasıl hesaplandığını gösterir.

```csharp
Document doc = new Document();

StructuredDocumentTag richText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(richText);

// Sağlama toplamı salt okunurdur ve karşılık gelen özel XML veri bölümünün verileri kullanılarak hesaplanır.
richText.XmlMapping.SetMapping(doc.CustomXmlParts.Add(Guid.NewGuid().ToString(),
    "<root><text>ContentControl</text></root>"), "/root/text", "");

long checksum = richText.XmlMapping.CustomXmlPart.DataChecksum;
Console.WriteLine(checksum);

richText.XmlMapping.SetMapping(doc.CustomXmlParts.Add(Guid.NewGuid().ToString(),
    "<root><text>Updated ContentControl</text></root>"), "/root/text", "");

long updatedChecksum = richText.XmlMapping.CustomXmlPart.DataChecksum;
Console.WriteLine(updatedChecksum);

// Etiketin XmlPart'ını değiştirdik ve sağlama toplamı çalışma zamanında güncellendi.
Assert.AreNotEqual(checksum, updatedChecksum);
```

### Ayrıca bakınız

* class [CustomXmlPart](../)
* ad alanı [Aspose.Words.Markup](../../customxmlpart/)
* toplantı [Aspose.Words](../../../)


