---
title: InlineStory.IsMoveFromRevision
second_title: Aspose.Words for .NET API Referansı
description: InlineStory mülk. İade doğru değişiklik izleme etkinken bu nesne Microsoft Wordde taşındıysa silindiyse.
type: docs
weight: 50
url: /tr/net/aspose.words/inlinestory/ismovefromrevision/
---
## InlineStory.IsMoveFromRevision property

İade **doğru** değişiklik izleme etkinken bu nesne Microsoft Word'de taşındıysa (silindiyse).

```csharp
public bool IsMoveFromRevision { get; }
```

### Örnekler

InlineStory düğümlerinin revizyonla ilgili özelliklerinin nasıl görüntüleneceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Revision footnotes.docx");

// Belgeyi düzenlediğimizde "Değişiklikleri İzle" seçeneği, İnceleme -> izleme,
// Microsoft Word'de açık, uyguladığımız değişiklikler revizyon olarak sayılır.
// Aspose.Words kullanarak bir belgeyi düzenlerken, revizyonları şu şekilde izlemeye başlayabiliriz:
// belgenin "StartTrackRevisions" yöntemini çağırarak ve "StopTrackRevisions" yöntemini kullanarak izlemeyi durdurun.
// Revizyonları belgeye asimile etmek için kabul edebiliriz
// veya önerilen değişikliği geri almak ve atmak için onları reddedin.
Assert.IsTrue(doc.HasRevisions);

List<Footnote> footnotes = doc.GetChildNodes(NodeType.Footnote, true).Cast<Footnote>().ToList();

Assert.AreEqual(5, footnotes.Count);

// Aşağıda, bir InlineStory düğümünü işaretleyebilen beş tür revizyon bulunmaktadır.
// 1 - Bir "insert" revizyonu:
// Bu revizyon, değişiklikleri takip ederken metin eklediğimizde gerçekleşir.
Assert.IsTrue(footnotes[2].IsInsertRevision);

// 2 - Bir "geçiş" revizyonu:
// Microsoft Word'de metni vurgulayıp belgede farklı bir yere sürüklediğimizde
// değişiklikleri takip ederken iki revizyon görünür.
// "Move from" revizyonu, metnin biz onu taşımadan önceki orijinal kopyasıdır.
Assert.IsTrue(footnotes[4].IsMoveFromRevision);

// 3 - "Taşı" revizyonu:
// "Taşı" revizyonu, belgedeki yeni konumuna taşıdığımız metindir.
// Yaptığımız her hareket revizyonu için "Move from" ve "move to" revizyonları çiftler halinde görünür.
// Bir taşıma revizyonunu kabul etmek, "move from" revizyonunu ve metnini siler,
// ve metni "move to" revizyonundan tutar.
// Bir taşıma revizyonunu reddetmek, tersine, "move from" revizyonunu korur ve "move to" revizyonunu siler.
Assert.IsTrue(footnotes[1].IsMoveToRevision);

// 4 - Bir "sil" revizyonu:
// Bu revizyon, değişiklikleri takip ederken metni sildiğimizde gerçekleşir. Böyle bir metni sildiğimizde,
// biz revizyonu kabul edene kadar belgede revizyon olarak kalacak,
// metni tamamen silecek veya düzeltmeyi reddedecek, bu da sildiğimiz metni olduğu yerde tutacak.
Assert.IsTrue(footnotes[3].IsDeleteRevision);
```

### Ayrıca bakınız

* class [InlineStory](../)
* ad alanı [Aspose.Words](../../inlinestory/)
* toplantı [Aspose.Words](../../../)


