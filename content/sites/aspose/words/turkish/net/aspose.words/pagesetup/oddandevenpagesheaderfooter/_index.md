---
title: PageSetup.OddAndEvenPagesHeaderFooter
second_title: Aspose.Words for .NET API Referansı
description: PageSetup mülk. Doğrubelgenin tek numaralı ve çift numaralı sayfalar için farklı üstbilgileri ve altbilgileri varsa.
type: docs
weight: 270
url: /tr/net/aspose.words/pagesetup/oddandevenpagesheaderfooter/
---
## PageSetup.OddAndEvenPagesHeaderFooter property

**Doğru**belgenin tek numaralı ve çift numaralı sayfalar için farklı üstbilgileri ve altbilgileri varsa.

```csharp
public bool OddAndEvenPagesHeaderFooter { get; set; }
```

### Notlar

Bu özelliğin değiştirilmesinin belgedeki tüm bölümleri etkilediğini unutmayın.

### Örnekler

DocumentBuilder kullanılarak bir belgede nasıl üstbilgi ve altbilgi oluşturulacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// İlk, çift ve tek sayfalar için farklı üstbilgi ve altbilgi istediğimizi belirtin.
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

// Başlıkları oluşturun, ardından her başlık türünü görüntülemek için belgeye üç sayfa ekleyin.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page3");

doc.Save(ArtifactsDir + "DocumentBuilder.HeadersAndFooters.docx");
```

Çift sayfa üstbilgilerinin/altbilgilerinin nasıl etkinleştirileceğini veya devre dışı bırakılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Aşağıda iki tür üstbilgi/altbilgi vardır.
// 1 - Bölümdeki her sayfada görünen "Birincil" üstbilgi/altbilgi.
// Birincil üstbilgiyi/altbilgiyi birinci ve çift sayfa üstbilgisi/altbilgisi ile geçersiz kılabiliriz.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Writeln("Primary header.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
builder.Writeln("Primary footer.");

// 2 - Bu bölümün her çift sayfasında görünen "Çift" üstbilgi/altbilgi.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Writeln("Even page header.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterEven);
builder.Writeln("Even page footer.");

builder.MoveToSection(0);
builder.Writeln("Page 1.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 2.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 3.");

// Her bölümün, sayfa görünümüyle ilgili özellikleri belirten bir "PageSetup" nesnesi vardır
// oryantasyon, boyut ve kenarlıklar gibi.
// "OddAndEvenPagesHeaderFooter" özelliğini "true" olarak ayarlayın
// çift sayfalarda çift sayfa üstbilgisini/altbilgisini görüntülemek için.
// "OddAndEvenPagesHeaderFooter" özelliğini "false" olarak ayarlayın
// çift sayfalarda birincil üstbilgi/altbilgiyi görüntülemek için.
builder.PageSetup.OddAndEvenPagesHeaderFooter = oddAndEvenPagesHeaderFooter;

doc.Save(ArtifactsDir + "PageSetup.OddAndEvenPagesHeaderFooter.docx");
```

### Ayrıca bakınız

* class [PageSetup](../)
* ad alanı [Aspose.Words](../../pagesetup/)
* toplantı [Aspose.Words](../../../)


