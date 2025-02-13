---
title: Enum RevisionsView
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.RevisionsView Sıralama. Bir belgenin orijinal sürümüyle mi yoksa gözden geçirilmiş sürümüyle mi çalışılacağını belirtmenize olanak tanır.
type: docs
weight: 4550
url: /tr/net/aspose.words/revisionsview/
---
## RevisionsView enumeration

Bir belgenin orijinal sürümüyle mi yoksa gözden geçirilmiş sürümüyle mi çalışılacağını belirtmenize olanak tanır.

```csharp
public enum RevisionsView
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| Original | `0` | Bir belgenin orijinal sürümünü belirtir. |
| Final | `1` | Bir belgenin gözden geçirilmiş sürümünü belirtir. |

### Örnekler

Bir belgenin gözden geçirilmiş ve orijinal görünümü arasında nasıl geçiş yapılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Revisions at list levels.docx");
doc.UpdateListLabels();

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual("1.", paragraphs[0].ListLabel.LabelString);
Assert.AreEqual("a.", paragraphs[1].ListLabel.LabelString);
Assert.AreEqual(string.Empty, paragraphs[2].ListLabel.LabelString);

// Belge nesnesini tüm revizyonlar kabul edilmiş gibi görüntüleyin. Şu anda liste etiketlerini destekler.
doc.RevisionsView = RevisionsView.Final;

Assert.AreEqual(string.Empty, paragraphs[0].ListLabel.LabelString);
Assert.AreEqual("1.", paragraphs[1].ListLabel.LabelString);
Assert.AreEqual("a.", paragraphs[2].ListLabel.LabelString);
```

### Ayrıca bakınız

* ad alanı [Aspose.Words](../../aspose.words/)
* toplantı [Aspose.Words](../../)


