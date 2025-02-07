---
title: Footnote.FootnoteType
second_title: Aspose.Words for .NET API Referansı
description: Footnote mülk. Bunun bir dipnot mu yoksa son not mu olduğunu belirten bir değer döndürür.
type: docs
weight: 20
url: /tr/net/aspose.words.notes/footnote/footnotetype/
---
## Footnote.FootnoteType property

Bunun bir dipnot mu yoksa son not mu olduğunu belirten bir değer döndürür.

```csharp
public FootnoteType FootnoteType { get; }
```

### Örnekler

Dipnotlar ve son notlar arasındaki farkı gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Metne numaralandırılmış referanslar eklemenin iki yolu aşağıdadır. Bu referansların her ikisi de bir
// onları eklediğimiz yerde küçük üst simge referans işareti.
// Referans işareti, varsayılan olarak, belgedeki tüm referanslar arasındaki referansın indeks numarasıdır.
// Her referans, gövde metnindekiyle aynı referans işaretine sahip olacak bir giriş de yaratacaktır.
// ve belge oluşturucunun "InsertFootnote" yöntemine ileteceğimiz referans metni.
// 1 - Girişi, referans verdiği metinle aynı sayfada görünecek bir dipnot:
builder.Write("Footnote referenced main body text.");
Footnote footnote = builder.InsertFootnote(FootnoteType.Footnote, 
    "Footnote text, will appear at the bottom of the page that contains the referenced text.");

// 2 - Girişi belgenin sonunda görünecek bir son not:
builder.Write("Endnote referenced main body text.");
Footnote endnote = builder.InsertFootnote(FootnoteType.Endnote, 
    "Endnote text, will appear at the very end of the document.");

builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.InsertBreak(BreakType.SectionBreakNewPage);

Assert.AreEqual(FootnoteType.Footnote, footnote.FootnoteType);
Assert.AreEqual(FootnoteType.Endnote, endnote.FootnoteType);

doc.Save(ArtifactsDir + "InlineStory.FootnoteEndnote.docx");
```

### Ayrıca bakınız

* enum [FootnoteType](../../footnotetype/)
* class [Footnote](../)
* ad alanı [Aspose.Words.Notes](../../footnote/)
* toplantı [Aspose.Words](../../../)


