---
title: ParagraphCollection.Item
second_title: Aspose.Words for .NET API Referansı
description: ParagraphCollection mülk. Bir Paragraf verilen dizinde.
type: docs
weight: 10
url: /tr/net/aspose.words/paragraphcollection/item/
---
## ParagraphCollection indexer

Bir **Paragraf** verilen dizinde.

```csharp
public Paragraph this[int index] { get; }
```

| Parametre | Tanım |
| --- | --- |
| index | Koleksiyona bir dizin. |

### Notlar

Endeks sıfır tabanlıdır.

Negatif dizinlere izin verilir ve koleksiyonun arkasından erişimi gösterir. Örneğin -1 son öğe anlamına gelir, -2 sondan önceki saniye anlamına gelir vb.

Dizin, listedeki öğe sayısından büyük veya ona eşitse, bu, boş bir başvuru döndürür.

İndeks negatifse ve mutlak değeri listedeki öğe sayısından büyükse, bu bir boş başvuru döndürür.

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

* class [Paragraph](../../paragraph/)
* class [ParagraphCollection](../)
* ad alanı [Aspose.Words](../../paragraphcollection/)
* toplantı [Aspose.Words](../../../)


