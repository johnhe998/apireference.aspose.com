---
title: Section.ClearHeadersFooters
second_title: Aspose.Words for .NET API Referansı
description: Section yöntem. Bu bölümün üstbilgilerini ve altbilgilerini temizler.
type: docs
weight: 100
url: /tr/net/aspose.words/section/clearheadersfooters/
---
## Section.ClearHeadersFooters method

Bu bölümün üstbilgilerini ve altbilgilerini temizler.

```csharp
public void ClearHeadersFooters()
```

### Notlar

Tüm üstbilgilerin ve altbilgilerin metni temizlenir, ancak[`HeaderFooter`](../../headerfooter/) nesnelerin kendileri kaldırılmaz.

Bu, bu bölümün üstbilgilerini ve altbilgilerini önceki bölümün üstbilgi ve altbilgilerine bağlı hale getirir.

### Örnekler

Bir bölümdeki tüm üstbilgilerin ve altbilgilerin içeriğinin nasıl temizleneceğini gösterir.

```csharp
Document doc = new Document();

Assert.AreEqual(0, doc.FirstSection.HeadersFooters.Count);

DocumentBuilder builder = new DocumentBuilder(doc);

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Writeln("This is the primary header.");
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
builder.Writeln("This is the primary footer.");

Assert.AreEqual(2, doc.FirstSection.HeadersFooters.Count);

Assert.AreEqual("This is the primary header.", doc.FirstSection.HeadersFooters[HeaderFooterType.HeaderPrimary].GetText().Trim());
Assert.AreEqual("This is the primary footer.", doc.FirstSection.HeadersFooters[HeaderFooterType.FooterPrimary].GetText().Trim());

// Bu bölümdeki tüm üstbilgileri ve altbilgileri tüm içeriklerinden boşaltın.
// Üstbilgiler ve altbilgiler hala mevcut olacak ancak görüntülenecek hiçbir şeyleri olmayacak.
doc.FirstSection.ClearHeadersFooters();

Assert.AreEqual(2, doc.FirstSection.HeadersFooters.Count);

Assert.AreEqual(string.Empty, doc.FirstSection.HeadersFooters[HeaderFooterType.HeaderPrimary].GetText().Trim());
Assert.AreEqual(string.Empty, doc.FirstSection.HeadersFooters[HeaderFooterType.FooterPrimary].GetText().Trim());
```

### Ayrıca bakınız

* class [Section](../)
* ad alanı [Aspose.Words](../../section/)
* toplantı [Aspose.Words](../../../)


