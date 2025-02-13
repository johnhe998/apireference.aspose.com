---
title: Class ParagraphCollection
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.ParagraphCollection sınıf. Bir koleksiyona yazılı erişim sağlarParagraph düğümler.
type: docs
weight: 4170
url: /tr/net/aspose.words/paragraphcollection/
---
## ParagraphCollection class

Bir koleksiyona yazılı erişim sağlar[`Paragraph`](../paragraph/) düğümler.

```csharp
public class ParagraphCollection : NodeCollection
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [Count](../../aspose.words/nodecollection/count/) { get; } | Koleksiyondaki düğüm sayısını alır. |
| [Item](../../aspose.words/paragraphcollection/item/) { get; } | Bir **Paragraf** verilen dizinde. (2 indexers) |

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
| [ToArray](../../aspose.words/paragraphcollection/toarray/#toarray_1)() | Koleksiyondaki tüm paragrafları yeni bir paragraf dizisine kopyalar. (2 methods) |

### Örnekler

Bir paragrafın taşıma revizyonu olup olmadığının nasıl kontrol edileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

// Bu belge, imleçle metni vurguladığımızda görünen "Taşı" revizyonlarını içerir,
// ve sonra başka bir konuma taşımak için sürükleyin
// Microsoft Word'de revizyonları "İnceleme" ile takip ederken -> "Parça değişiklikleri".
Assert.AreEqual(6, doc.Revisions.Count(r => r.RevisionType == RevisionType.Moving));

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

// Revizyonları taşıma, "Taşı" ve "Taşı" revizyonlarından oluşur. 
// Bu revizyonlar, belgede kabul edebileceğimiz veya reddedebileceğimiz olası değişikliklerdir.
// Bir taşıma revizyonunu kabul etmeden/reddetmeden önce, belge
// metnin hem kalkış hem de varış yerlerini takip etmelidir.
// İkinci ve dördüncü paragraf böyle bir revizyonu tanımlar ve bu nedenle her ikisi de aynı içeriğe sahiptir.
Assert.AreEqual(paragraphs[1].GetText(), paragraphs[3].GetText());

// "Taşı" revizyonu, metni sürüklediğimiz paragraftır.
// Revizyonu kabul edersek bu paragraf kaybolacak,
// ve diğeri kalacak ve artık bir revizyon olmayacak.
Assert.True(paragraphs[1].IsMoveFromRevision);

// "Taşı" revizyonu, metni sürüklediğimiz paragraftır.
// Revizyonu reddedersek, bunun yerine bu paragraf kaybolacak ve diğeri kalacaktır.
Assert.True(paragraphs[3].IsMoveToRevision);
```

### Ayrıca bakınız

* class [NodeCollection](../nodecollection/)
* ad alanı [Aspose.Words](../../aspose.words/)
* toplantı [Aspose.Words](../../)


