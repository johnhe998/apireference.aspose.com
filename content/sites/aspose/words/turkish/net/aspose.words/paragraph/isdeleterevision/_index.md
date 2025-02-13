---
title: Paragraph.IsDeleteRevision
second_title: Aspose.Words for .NET API Referansı
description: Paragraph mülk. Bu nesne değişiklik izleme etkinleştirilirken Microsoft Wordde silindiyse true değerini döndürür.
type: docs
weight: 40
url: /tr/net/aspose.words/paragraph/isdeleterevision/
---
## Paragraph.IsDeleteRevision property

Bu nesne, değişiklik izleme etkinleştirilirken Microsoft Word'de silindiyse true değerini döndürür.

```csharp
public bool IsDeleteRevision { get; }
```

### Örnekler

Revizyon paragraflarıyla nasıl çalışılacağını gösterir.

```csharp
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

// Yukarıdaki paragraflar revizyon değildir.
// Revizyon takibi başladıktan sonra eklediğimiz paragraflar "Ekle" revizyonları olarak kayıt edilecektir.
doc.StartTrackRevisions("John Doe", DateTime.Now);

para = body.AppendParagraph("Paragraph 4. ");

Assert.True(para.IsInsertRevision);

// Revizyon takibini başlattıktan sonra kaldırdığımız paragraflar "Sil" revizyonları olarak kaydedilecektir.
ParagraphCollection paragraphs = body.Paragraphs;

Assert.AreEqual(4, paragraphs.Count);

para = paragraphs[2];
para.Remove();

// Bu tür paragraflar, silme revizyonunu kabul edene veya reddedene kadar kalacaktır.
// Revizyonu kabul etmek paragrafı tamamen kaldıracak,
// ve revizyonu reddetmek, onu sanki hiç silmemişiz gibi belgede bırakacaktır.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// Revizyonu kabul edin ve ardından paragrafın gittiğini doğrulayın.
doc.AcceptAllRevisions();

Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
Assert.AreEqual(
    "Paragraph 1. \r" +
    "Paragraph 2. \r" +
    "Paragraph 4.", doc.GetText().Trim());
```

### Ayrıca bakınız

* class [Paragraph](../)
* ad alanı [Aspose.Words](../../paragraph/)
* toplantı [Aspose.Words](../../../)


