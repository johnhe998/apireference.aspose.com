---
title: Class SectionCollection
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.SectionCollection sınıf. Bir koleksiyon Bölüm belgedeki nesneler.
type: docs
weight: 5450
url: /tr/net/aspose.words/sectioncollection/
---
## SectionCollection class

Bir koleksiyon **Bölüm** belgedeki nesneler.

```csharp
public class SectionCollection : NodeCollection
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [Count](../../aspose.words/nodecollection/count/) { get; } | Koleksiyondaki düğüm sayısını alır. |
| [Item](../../aspose.words/sectioncollection/item/) { get; } | Verilen dizindeki bir bölümü alır. (2 indexers) |

## yöntemler

| İsim | Tanım |
| --- | --- |
| [Add](../../aspose.words/nodecollection/add/)(Node) | Koleksiyonun sonuna bir düğüm ekler. |
| [Clear](../../aspose.words/nodecollection/clear/)() | Bu koleksiyondaki ve belgedeki tüm düğümleri kaldırır. |
| [Contains](../../aspose.words/nodecollection/contains/)(Node) | Koleksiyonda bir düğüm olup olmadığını belirler. |
| [GetEnumerator](../../aspose.words/nodecollection/getenumerator/)() | Düğüm koleksiyonu üzerinde basit bir "foreach" stili yineleme sağlar. |
| [IndexOf](../../aspose.words/nodecollection/indexof/)(Node) | Belirtilen düğümün sıfır tabanlı dizinini döndürür. |
| [Insert](../../aspose.words/nodecollection/insert/)(int, Node) | Belirtilen dizindeki koleksiyona bir düğüm ekler. |
| [Remove](../../aspose.words/nodecollection/remove/)(Node) | Düğümü koleksiyondan ve belgeden kaldırır. |
| [RemoveAt](../../aspose.words/nodecollection/removeat/)(int) | Belirtilen dizindeki düğümü koleksiyondan ve belgeden kaldırır. |
| [ToArray](../../aspose.words/sectioncollection/toarray/#toarray_1)() | Koleksiyondaki tüm bölümleri yeni bir bölüm dizisine kopyalar. (2 methods) |

### Notlar

Bir Microsoft Word belgesi birden çok bölüm içerebilir. Microsoft Word'de bir bölüm oluşturmak için, Ekle/Break komutunu seçin ve bir kesme türü seçin. Ara, bölümün yeni bir sayfada mı yoksa aynı sayfada mı start olacağını belirtir.

Bölümleri programlı olarak ekleme ve kaldırma, adres mektup birleştirme sırasında üretilen belgelerini özelleştirmek için kullanılabilir. Bir belgenin bazı ölçütlere bağlı olarak farklı içeriğe veya içeriğinin bölümlerine sahip olması gerekiyorsa, birden çok bölümü içeren bir "ana" belge oluşturabilir ve adres mektup birleştirmeden önce veya sonra bazı bölümleri silebilirsiniz.

### Örnekler

Bir belgeye bölümlerin nasıl ekleneceğini ve kaldırılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Section 1");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Section 2");

Assert.AreEqual("Section 1\x000cSection 2", doc.GetText().Trim());

// İlk bölümü belgeden silin.
doc.Sections.RemoveAt(0);

Assert.AreEqual("Section 2", doc.GetText().Trim());

// Şimdi ilk bölümün bir kopyasını belgenin sonuna ekleyin.
int lastSectionIdx = doc.Sections.Count - 1;
Section newSection = doc.Sections[lastSectionIdx].Clone();
doc.Sections.Add(newSection);

Assert.AreEqual("Section 2\x000cSection 2", doc.GetText().Trim());
```

### Ayrıca bakınız

* class [NodeCollection](../nodecollection/)
* ad alanı [Aspose.Words](../../aspose.words/)
* toplantı [Aspose.Words](../../)


