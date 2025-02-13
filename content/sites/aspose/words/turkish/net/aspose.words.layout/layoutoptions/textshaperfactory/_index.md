---
title: LayoutOptions.TextShaperFactory
second_title: Aspose.Words for .NET API Referansı
description: LayoutOptions mülk. Alır veya ayarlarITextShaperFactory Gelişmiş Tipografi oluşturma özellikleri için kullanılan uygulama.
type: docs
weight: 90
url: /tr/net/aspose.words.layout/layoutoptions/textshaperfactory/
---
## LayoutOptions.TextShaperFactory property

Alır veya ayarlar[`ITextShaperFactory`](../../../aspose.words.shaping/itextshaperfactory/) Gelişmiş Tipografi oluşturma özellikleri için kullanılan uygulama.

```csharp
public ITextShaperFactory TextShaperFactory { get; set; }
```

### Örnekler

HarfBuzz metin şekillendirme motorunu kullanarak OpenType özelliklerinin nasıl destekleneceğini gösterir.

```csharp
Document doc = new Document(MyDir + "OpenType text shaping.docx");

// Aspose.Words harici olarak sağlanan metin şekillendirici nesneleri kullanabilir,
// yazı tiplerini temsil eden ve metin için şekillendirme bilgilerini hesaplayan.
// Birden çok yazı tipi kullanan belgeler için bir metin şekillendirici fabrikası gereklidir.
// Metin şekillendirici fabrika ayarlandığında, düzen OpenType özelliklerini kullanır.
// Bir Instance özelliği, HarfBuzzTextShaperFactory sarmalayan statik bir BasicTextShaperCache nesnesi döndürür.
doc.LayoutOptions.TextShaperFactory = HarfBuzzTextShaperFactory.Instance;

// Şu anda, PDF veya XPS biçimlerine dışa aktarırken metin şekillendirme gerçekleştiriliyor.
doc.Save(ArtifactsDir + "Document.OpenType.pdf");
```

### Ayrıca bakınız

* interface [ITextShaperFactory](../../../aspose.words.shaping/itextshaperfactory/)
* class [LayoutOptions](../)
* ad alanı [Aspose.Words.Layout](../../layoutoptions/)
* toplantı [Aspose.Words](../../../)


