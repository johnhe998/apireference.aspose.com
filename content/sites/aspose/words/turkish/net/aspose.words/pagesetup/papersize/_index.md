---
title: PageSetup.PaperSize
second_title: Aspose.Words for .NET API Referansı
description: PageSetup mülk. Kağıt boyutunu döndürür veya ayarlar.
type: docs
weight: 340
url: /tr/net/aspose.words/pagesetup/papersize/
---
## PageSetup.PaperSize property

Kağıt boyutunu döndürür veya ayarlar.

```csharp
public PaperSize PaperSize { get; set; }
```

### Notlar

Bu özellik güncellemelerini ayarlama[`PageWidth`](../pagewidth/) ve[`PageHeight`](../pageheight/) değerleri. Bu değerin ayarlanmasıCustom mevcut değerleri değiştirmez.

### Örnekler

Bir bölüm için diğer ayarlarla birlikte kağıt boyutunun, yönün, kenar boşluklarının nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.PageSetup.PaperSize = PaperSize.Legal;
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
builder.PageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
builder.PageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
builder.PageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
builder.PageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
builder.PageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);

builder.Writeln("Hello world!");

doc.Save(ArtifactsDir + "PageSetup.PageMargins.docx");
```

Sayfa boyutlarının nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Mevcut sayfanın boyutunu önceden tanımlanmış bir boyuta değiştirebiliriz
// bu bölümün PageSetup nesnesinin "PaperSize" özelliğini kullanarak.
builder.PageSetup.PaperSize = PaperSize.Tabloid;

Assert.AreEqual(792.0d, builder.PageSetup.PageWidth);
Assert.AreEqual(1224.0d, builder.PageSetup.PageHeight);

builder.Writeln($"This page is {builder.PageSetup.PageWidth}x{builder.PageSetup.PageHeight}.");

// Her bölümün kendi PageSetup nesnesi vardır. Yeni bir bölüm oluşturmak için bir belge oluşturucu kullandığımızda,
// bu bölümün PageSetup nesnesi, önceki bölümün tüm PageSetup nesnesinin değerlerini devralır.
builder.InsertBreak(BreakType.SectionBreakEvenPage);

Assert.AreEqual(PaperSize.Tabloid, builder.PageSetup.PaperSize);

builder.PageSetup.PaperSize = PaperSize.A5;
builder.Writeln($"This page is {builder.PageSetup.PageWidth}x{builder.PageSetup.PageHeight}.");

Assert.AreEqual(419.55d, builder.PageSetup.PageWidth);
Assert.AreEqual(595.30d, builder.PageSetup.PageHeight);

builder.InsertBreak(BreakType.SectionBreakEvenPage);

// Bu bölümün sayfaları için özel bir boyut ayarlayın.
builder.PageSetup.PageWidth = 620;
builder.PageSetup.PageHeight = 480;

Assert.AreEqual(PaperSize.Custom, builder.PageSetup.PaperSize);

builder.Writeln($"This page is {builder.PageSetup.PageWidth}x{builder.PageSetup.PageHeight}.");

doc.Save(ArtifactsDir + "PageSetup.PaperSizes.docx");
```

Bir Aspose.Words belgesinin elle nasıl oluşturulacağını gösterir.

```csharp
Document doc = new Document();

// Boş bir belge bir bölüm, bir gövde ve bir paragraf içerir.
// Tüm bu düğümleri kaldırmak için "RemoveAllChildren" yöntemini çağırın,
// ve alt öğesi olmayan bir belge düğümüyle bitirin.
doc.RemoveAllChildren();

// Bu belgede artık içerik ekleyebileceğimiz bileşik alt düğüm yok.
// Düzenlemek istiyorsak, düğüm koleksiyonunu yeniden doldurmamız gerekecek.
// Önce yeni bir bölüm oluşturun ve ardından onu kök belge düğümüne alt öğe olarak ekleyin.
Section section = new Section(doc);
doc.AppendChild(section);

// Bölüm için bazı sayfa kurulum özelliklerini ayarlayın.
section.PageSetup.SectionStart = SectionStart.NewPage;
section.PageSetup.PaperSize = PaperSize.Letter;

// Bir bölümün tüm içeriğini içerecek ve görüntüleyecek bir gövdeye ihtiyacı var
// bölümün üstbilgisi ve altbilgisi arasındaki sayfada.
Body body = new Body(doc);
section.AppendChild(body);

// Bir paragraf oluşturun, bazı biçimlendirme özelliklerini ayarlayın ve ardından onu alt öğe olarak gövdeye ekleyin.
Paragraph para = new Paragraph(doc);

para.ParagraphFormat.StyleName = "Heading 1";
para.ParagraphFormat.Alignment = ParagraphAlignment.Center;

body.AppendChild(para);

// Son olarak, belgeyi yapmak için biraz içerik ekleyin. Bir koşu oluşturun,
// görünümünü ve içeriğini ayarlayın ve ardından paragrafa alt öğe olarak ekleyin.
Run run = new Run(doc);
run.Text = "Hello World!";
run.Font.Color = Color.Red;
para.AppendChild(run);

Assert.AreEqual("Hello World!", doc.GetText().Trim());

doc.Save(ArtifactsDir + "Section.CreateManually.docx");
```

### Ayrıca bakınız

* enum [PaperSize](../../papersize/)
* class [PageSetup](../)
* ad alanı [Aspose.Words](../../pagesetup/)
* toplantı [Aspose.Words](../../../)


