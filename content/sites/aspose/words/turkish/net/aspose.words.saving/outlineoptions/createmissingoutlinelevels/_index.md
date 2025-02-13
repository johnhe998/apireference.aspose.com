---
title: OutlineOptions.CreateMissingOutlineLevels
second_title: Aspose.Words for .NET API Referansı
description: OutlineOptions mülk. Belge dışa aktarıldığında eksik anahat düzeylerinin oluşturulup oluşturulmayacağını belirleyen bir değer alır veya ayarlar.
type: docs
weight: 30
url: /tr/net/aspose.words.saving/outlineoptions/createmissingoutlinelevels/
---
## OutlineOptions.CreateMissingOutlineLevels property

Belge dışa aktarıldığında eksik anahat düzeylerinin oluşturulup oluşturulmayacağını belirleyen bir değer alır veya ayarlar.

Bu özellik için varsayılan değer **yanlış**.

```csharp
public bool CreateMissingOutlineLevels { get; set; }
```

### Örnekler

Bir PDF belgesini kaydederken karşılık gelen herhangi bir başlık içermeyen anahat düzeyleriyle nasıl çalışılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Seviye 1 ve 5'in İçindekiler girişi olarak hizmet edebilecek başlıklar ekleyin.
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

Assert.True(builder.ParagraphFormat.IsHeading);

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading5;

builder.Writeln("Heading 1.1.1.1.1");
builder.Writeln("Heading 1.1.1.1.2");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "PdfSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi .PDF'ye dönüştürme şeklini değiştirmek için.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Çıktı PDF belgesi, belge gövdesindeki başlıkları listeleyen bir içindekiler tablosu olan bir anahat içerecektir.
// Bu taslakta bir girdiye tıklamak bizi ilgili başlığın konumuna götürecektir.
// Seviye 5 ve altındaki tüm başlıkları anahatta dahil etmek için "HeadingsOutlineLevels" özelliğini "5" olarak ayarlayın.
saveOptions.OutlineOptions.HeadingsOutlineLevels = 5;

 // Bu belge 1. ve 5. düzey başlıklar içerir ve 2., 3. ve 4. düzey başlıklar içermez.
// Çıktı PDF belgesi, 2, 3 ve 4 anahat düzeylerini "eksik" olarak değerlendirecektir.
// Anahatta tüm eksik seviyeleri dahil etmek için "CreateMissingOutlineLevels" özelliğini "true" olarak ayarlayın,
// Kullanılabilir başlık olmadığı için anahat girişlerini boş bırakıyoruz.
// Eksik anahat düzeylerini yok saymak için "CreateMissingOutlineLevels" özelliğini "false" olarak ayarlayın,
// ve anahat seviyesi 5 başlıklarını seviye 2 olarak ele alın.
saveOptions.OutlineOptions.CreateMissingOutlineLevels = createMissingOutlineLevels;

doc.Save(ArtifactsDir + "PdfSaveOptions.CreateMissingOutlineLevels.pdf", saveOptions);
```

### Ayrıca bakınız

* class [OutlineOptions](../)
* ad alanı [Aspose.Words.Saving](../../outlineoptions/)
* toplantı [Aspose.Words](../../../)


