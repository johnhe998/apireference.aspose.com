---
title: Story.Paragraphs
second_title: Aspose.Words for .NET API Referansı
description: Story mülk. Öykünün doğrudan alt öğeleri olan bir paragraf koleksiyonu alır.
type: docs
weight: 30
url: /tr/net/aspose.words/story/paragraphs/
---
## Story.Paragraphs property

Öykünün doğrudan alt öğeleri olan bir paragraf koleksiyonu alır.

```csharp
public ParagraphCollection Paragraphs { get; }
```

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

* class [ParagraphCollection](../../paragraphcollection/)
* class [Story](../)
* ad alanı [Aspose.Words](../../story/)
* toplantı [Aspose.Words](../../../)


