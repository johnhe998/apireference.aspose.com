---
title: Paragraph.IsFormatRevision
second_title: Aspose.Words for .NET API Referansı
description: Paragraph mülk. Değişiklik izleme etkinken nesnenin biçimlendirmesi Microsoft Wordde değiştirilirse doğru döndürür.
type: docs
weight: 90
url: /tr/net/aspose.words/paragraph/isformatrevision/
---
## Paragraph.IsFormatRevision property

Değişiklik izleme etkinken nesnenin biçimlendirmesi Microsoft Word'de değiştirilirse doğru döndürür.

```csharp
public bool IsFormatRevision { get; }
```

### Örnekler

Bir paragrafın biçim revizyonu olup olmadığının nasıl kontrol edileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Format revision.docx");

// Bu paragraf, mevcut metnin biçimlendirmesini değiştirdiğimizde ortaya çıkan bir "Biçim" revizyonudur.
// Microsoft Word'de revizyonları "İnceleme" ile takip ederken -> "Parça değişiklikleri".
Assert.True(doc.FirstSection.Body.FirstParagraph.IsFormatRevision);
```

### Ayrıca bakınız

* class [Paragraph](../)
* ad alanı [Aspose.Words](../../paragraph/)
* toplantı [Aspose.Words](../../../)


