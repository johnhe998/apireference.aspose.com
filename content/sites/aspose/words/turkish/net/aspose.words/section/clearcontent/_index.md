---
title: Section.ClearContent
second_title: Aspose.Words for .NET API Referansı
description: Section yöntem. Bölümü temizler.
type: docs
weight: 90
url: /tr/net/aspose.words/section/clearcontent/
---
## Section.ClearContent method

Bölümü temizler.

```csharp
public void ClearContent()
```

### Notlar

metni[`Body`](../body/) temizlenirse, bölüm sonunu temsil eden yalnızca bir boş paragraf kalır.

Tüm üstbilgilerin ve altbilgilerin metni temizlenir, ancak[`HeaderFooter`](../../headerfooter/) nesnelerin kendileri kaldırılmaz.

### Örnekler

Bir bölümün içeriğinin nasıl temizleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Hello world!");

Assert.AreEqual("Hello world!", doc.GetText().Trim());
Assert.AreEqual(1, doc.FirstSection.Body.Paragraphs.Count);

// "ClearContent" yöntemini çalıştırmak tüm bölüm içeriğini kaldıracak
// ancak tekrar içerik eklemek için boş bir paragraf bırakın.
doc.FirstSection.ClearContent();

Assert.AreEqual(string.Empty, doc.GetText().Trim());
Assert.AreEqual(1, doc.FirstSection.Body.Paragraphs.Count);
```

### Ayrıca bakınız

* class [Section](../)
* ad alanı [Aspose.Words](../../section/)
* toplantı [Aspose.Words](../../../)


