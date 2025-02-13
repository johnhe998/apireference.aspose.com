---
title: Font.Shading
second_title: Aspose.Words for .NET API Referansı
description: Font mülk. Yazı tipi için gölgeleme biçimlendirmesine başvuran bir Shading nesnesi döndürür.
type: docs
weight: 320
url: /tr/net/aspose.words/font/shading/
---
## Font.Shading property

Yazı tipi için gölgeleme biçimlendirmesine başvuran bir Shading nesnesi döndürür.

```csharp
public Shading Shading { get; }
```

### Örnekler

Belge oluşturucu tarafından oluşturulan metne gölgelendirmenin nasıl uygulanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Color = Color.White;

// Beyaz yazı tipi rengimizi kullanarak oluşturulan metni görünür kılmanın bir yolu
// bir arka plan gölgelendirme efekti uygulamaktır.
Shading shading = builder.Font.Shading;
shading.Texture = TextureIndex.TextureDiagonalUp;
shading.BackgroundPatternColor = Color.OrangeRed;
shading.ForegroundPatternColor = Color.DarkBlue;

builder.Writeln("White text on an orange background with a two-tone texture.");

doc.Save(ArtifactsDir + "Font.Shading.docx");
```

### Ayrıca bakınız

* class [Shading](../../shading/)
* class [Font](../)
* ad alanı [Aspose.Words](../../font/)
* toplantı [Aspose.Words](../../../)


