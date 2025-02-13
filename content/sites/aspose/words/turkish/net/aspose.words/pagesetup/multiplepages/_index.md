---
title: PageSetup.MultiplePages
second_title: Aspose.Words for .NET API Referansı
description: PageSetup mülk. Çok sayfalı belgeler için bir belgenin kitapçık olarak ciltlenebilmesi için nasıl yazdırılacağını veya oluşturulacağını alır veya ayarlar.
type: docs
weight: 260
url: /tr/net/aspose.words/pagesetup/multiplepages/
---
## PageSetup.MultiplePages property

Çok sayfalı belgeler için, bir belgenin kitapçık olarak ciltlenebilmesi için nasıl yazdırılacağını veya oluşturulacağını alır veya ayarlar.

```csharp
public MultiplePagesType MultiplePages { get; set; }
```

### Örnekler

Kitap katlama olarak yazdırılabilen bir belgenin nasıl yapılandırılacağını gösterir.

```csharp
Document doc = new Document();

// 16 sayfaya yayılan metin ekleyin.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("My Booklet:");

for (int i = 0; i < 15; i++)
{
    builder.InsertBreak(BreakType.PageBreak);
    builder.Write($"Booklet face #{i}");
}

// Belgeyi kitap katlama biçiminde yazdırmak için ilk bölümün "PageSetup" özelliğini yapılandırın.
// Bu belgeyi her iki tarafa yazdırdığımızda, sayfaları istiflemek için alabiliriz
// ve hepsini bir kerede ortadan katlayın. Belgenin içeriği bir kitap katlaması şeklinde sıralanacaktır.
PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.MultiplePages = MultiplePagesType.BookFoldPrinting;

// Sayfa sayısını sadece 4'ün katları olarak belirtebiliriz.
pageSetup.SheetsPerBooklet = 4;

doc.Save(ArtifactsDir + "PageSetup.Booklet.docx");
```

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

* enum [MultiplePagesType](../../../aspose.words.settings/multiplepagestype/)
* class [PageSetup](../)
* ad alanı [Aspose.Words](../../pagesetup/)
* toplantı [Aspose.Words](../../../)


