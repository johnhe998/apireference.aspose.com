---
title: HtmlLoadOptions.SupportVml
second_title: Aspose.Words for .NET API Referansı
description: HtmlLoadOptions mülk. VML görüntülerinin desteklenip desteklenmediğini belirten bir değer alır veya ayarlar.
type: docs
weight: 60
url: /tr/net/aspose.words.loading/htmlloadoptions/supportvml/
---
## HtmlLoadOptions.SupportVml property

VML görüntülerinin desteklenip desteklenmediğini belirten bir değer alır veya ayarlar.

```csharp
public bool SupportVml { get; set; }
```

### Örnekler

Bir HTML belgesi yüklenirken koşullu yorumların nasıl destekleneceğini gösterir.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions();

// Değer true ise yüklenen belgeyi ayrıştırırken VML kodunu dikkate alıyoruz.
loadOptions.SupportVml = supportVml;

// Bu belge, "<!--[if gte vml 1]>" içinde bir JPEG resmi içeriyor etiketler,
// ve "<![if !vml]>" içinde farklı bir PNG resmi etiketler.
// "SupportVml" bayrağını "true" olarak ayarlarsak Aspose.Words JPEG'i yükleyecektir.
// Bu bayrağı "false" olarak ayarlarsak Aspose.Words sadece PNG'yi yükler.
Document doc = new Document(MyDir + "VML conditional.htm", loadOptions);

if (supportVml)
    Assert.AreEqual(ImageType.Jpeg, ((Shape)doc.GetChild(NodeType.Shape, 0, true)).ImageData.ImageType);
else
    Assert.AreEqual(ImageType.Png, ((Shape)doc.GetChild(NodeType.Shape, 0, true)).ImageData.ImageType);
```

### Ayrıca bakınız

* class [HtmlLoadOptions](../)
* ad alanı [Aspose.Words.Loading](../../htmlloadoptions/)
* toplantı [Aspose.Words](../../../)


