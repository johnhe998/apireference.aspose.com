---
title: CustomXmlPropertyCollection.GetEnumerator
second_title: Aspose.Words for .NET API Referansı
description: CustomXmlPropertyCollection yöntem. Koleksiyondaki tüm öğeler üzerinde yineleme yapmak için kullanılabilecek bir Numaralandırıcı nesnesi döndürür.
type: docs
weight: 60
url: /tr/net/aspose.words.markup/customxmlpropertycollection/getenumerator/
---
## CustomXmlPropertyCollection.GetEnumerator method

Koleksiyondaki tüm öğeler üzerinde yineleme yapmak için kullanılabilecek bir Numaralandırıcı nesnesi döndürür.

```csharp
public IEnumerator<CustomXmlProperty> GetEnumerator()
```

### Örnekler

Akıllı etiketler hakkında derinlemesine bilgi almak için akıllı etiket özellikleriyle nasıl çalışılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Smart tags.doc");

// Microsoft Word ile bir belgede bir akıllı etiket görünür, metninin bir bölümünü bir tür veri olarak tanır,
// ad, tarih veya adres gibi ve onu mor noktalı alt çizgi görüntüleyen bir köprüye dönüştürür.
// Word 2003'te akıllı etiketleri "Araçlar" -> "Otomatik Düzeltme seçenekleri..." -> "Akıllı Etiketler".
// Girdi belgemizde, Microsoft Word'ün akıllı etiketler olarak kaydettiği üç nesne var.
// Akıllı etiketler iç içe yerleştirilebilir, bu nedenle bu koleksiyon daha fazlasını içerir.
SmartTag[] smartTags = doc.GetChildNodes(NodeType.SmartTag, true).OfType<SmartTag>().ToArray();

Assert.AreEqual(8, smartTags.Length);

// Bir akıllı etiketin "Özellikler" üyesi, her akıllı etiket türü için farklı olacak olan meta verilerini içerir.
// Bir "tarih" tipi akıllı etiketin özellikleri, onun yılını, ayını ve gününü içerir.
CustomXmlPropertyCollection properties = smartTags[7].Properties;

Assert.AreEqual(4, properties.Count);

using (IEnumerator<CustomXmlProperty> enumerator = properties.GetEnumerator())
{
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Property name: {enumerator.Current.Name}, value: {enumerator.Current.Value}");
        Assert.AreEqual("", enumerator.Current.Uri);
    }
}

// Özelliklere, anahtar/değer çifti gibi çeşitli yollarla da erişebiliriz.
Assert.True(properties.Contains("Day"));
Assert.AreEqual("22", properties["Day"].Value);
Assert.AreEqual("2003", properties[2].Value);
Assert.AreEqual(1, properties.IndexOfKey("Month"));

// Aşağıda, özellikler koleksiyonundan öğeleri kaldırmanın üç yolu vardır.
// 1 - Dizine göre kaldır:
properties.RemoveAt(3);

Assert.AreEqual(3, properties.Count);

// 2 - Ada göre kaldır:
properties.Remove("Year");

Assert.AreEqual(2, properties.Count);

// 3 - Tüm koleksiyonu bir kerede temizle:
properties.Clear();

Assert.AreEqual(0, properties.Count);
```

### Ayrıca bakınız

* class [CustomXmlProperty](../../customxmlproperty/)
* class [CustomXmlPropertyCollection](../)
* ad alanı [Aspose.Words.Markup](../../customxmlpropertycollection/)
* toplantı [Aspose.Words](../../../)


