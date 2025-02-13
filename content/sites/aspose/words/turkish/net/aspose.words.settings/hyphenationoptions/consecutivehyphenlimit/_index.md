---
title: HyphenationOptions.ConsecutiveHyphenLimit
second_title: Aspose.Words for .NET API Referansı
description: HyphenationOptions mülk. Kısa çizgi ile bitebilecek maksimum ardışık satır sayısını alır veya ayarlar. Bu özellik için varsayılan değer 0.
type: docs
weight: 30
url: /tr/net/aspose.words.settings/hyphenationoptions/consecutivehyphenlimit/
---
## HyphenationOptions.ConsecutiveHyphenLimit property

Kısa çizgi ile bitebilecek maksimum ardışık satır sayısını alır veya ayarlar. Bu özellik için varsayılan değer 0.

```csharp
public int ConsecutiveHyphenLimit { get; set; }
```

### Notlar

Bu özelliğin değeri 0 olarak ayarlanırsa, herhangi bir sayıda ardışık satır kısa çizgi ile bitebilir.

Özelliğin, örneğin PDF gibi sabit sayfa biçimlerine kaydederken etkisi yoktur.

### Örnekler

Otomatik tirelemenin nasıl yapılandırılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Size = 24;
builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

doc.HyphenationOptions.AutoHyphenation = true;
doc.HyphenationOptions.ConsecutiveHyphenLimit = 2;
doc.HyphenationOptions.HyphenationZone = 720;
doc.HyphenationOptions.HyphenateCaps = true;

doc.Save(ArtifactsDir + "Document.HyphenationOptions.docx");
```

### Ayrıca bakınız

* class [HyphenationOptions](../)
* ad alanı [Aspose.Words.Settings](../../hyphenationoptions/)
* toplantı [Aspose.Words](../../../)


