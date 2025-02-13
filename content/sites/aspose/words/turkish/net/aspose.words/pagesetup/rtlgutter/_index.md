---
title: PageSetup.RtlGutter
second_title: Aspose.Words for .NET API Referansı
description: PageSetup mülk. Microsoft Wordün bölüm için sağdan sola mı yoksa soldan sağa bir dile göre mi oluklar kullanacağını alır veya ayarlar.
type: docs
weight: 370
url: /tr/net/aspose.words/pagesetup/rtlgutter/
---
## PageSetup.RtlGutter property

Microsoft Word'ün bölüm için sağdan sola mı yoksa soldan sağa bir dile göre mi oluklar kullanacağını alır veya ayarlar.

```csharp
public bool RtlGutter { get; set; }
```

### Örnekler

Oluk kenar boşluklarının nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();

// Birkaç sayfaya yayılan metin ekleyin.
DocumentBuilder builder = new DocumentBuilder(doc);
for (int i = 0; i < 6; i++)
{
    builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                  "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");
    builder.InsertBreak(BreakType.PageBreak);
}

// Bir cilt payı, sayfanın sol veya sağ kenar boşluğuna boşluk ekler,
// bu, sayfa düzenini ihlal eden bir kitaptaki sayfaların ortadan katlanmasını telafi eder.
PageSetup pageSetup = doc.Sections[0].PageSetup;

 // Sayfalarımızın kenar boşlukları içinde metin için ne kadar alana sahip olduğunu belirleyin ve ardından bir kenar boşluğunu doldurmak için bir miktar ekleyin.
Assert.AreEqual(470.30d, pageSetup.PageWidth - pageSetup.LeftMargin - pageSetup.RightMargin, 0.01d);

pageSetup.Gutter = 100.0d;

// Sağdan sola yazılan metin için cilt payını daha uygun bir konuma yerleştirmek için "RtlGutter" özelliğini "true" olarak ayarlayın.
pageSetup.RtlGutter = true;

// Alternatif olarak "MultiplePages" özelliğini "MultiplePagesType.MirrorMargins" olarak ayarlayın
// her sayfada kenar boşluklarının sol/sağ sayfa tarafı konumu.
pageSetup.MultiplePages = MultiplePagesType.MirrorMargins;

doc.Save(ArtifactsDir + "PageSetup.Gutter.docx");
```

### Ayrıca bakınız

* class [PageSetup](../)
* ad alanı [Aspose.Words](../../pagesetup/)
* toplantı [Aspose.Words](../../../)


