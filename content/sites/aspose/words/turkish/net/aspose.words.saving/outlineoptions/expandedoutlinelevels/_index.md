---
title: OutlineOptions.ExpandedOutlineLevels
second_title: Aspose.Words for .NET API Referansı
description: OutlineOptions mülk. Dosya görüntülendiğinde genişletilmiş belge anahattında kaç düzeyin gösterileceğini belirtir.
type: docs
weight: 60
url: /tr/net/aspose.words.saving/outlineoptions/expandedoutlinelevels/
---
## OutlineOptions.ExpandedOutlineLevels property

Dosya görüntülendiğinde genişletilmiş belge anahattında kaç düzeyin gösterileceğini belirtir.

```csharp
public int ExpandedOutlineLevels { get; set; }
```

### Notlar

Bu seçeneklerin XPS'e kaydederken çalışmayacağını unutmayın.

0 belirtin ve belge taslağı daraltılacaktır; 1 belirtin ve anahatta ilk seviye item genişletilecek ve bu böyle devam edecek.

Varsayılan 0'dır. Geçerli aralık 0 ila 9'dur.

### Örnekler

Belge anahattında üç düzeyle bir belgenin tamamının PDF'ye nasıl dönüştürüleceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 1'den 5'e kadar olan seviyelerin başlıklarını ekleyin.
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

Assert.True(builder.ParagraphFormat.IsHeading);

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 1.2.1");
builder.Writeln("Heading 1.2.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading4;

builder.Writeln("Heading 1.2.2.1");
builder.Writeln("Heading 1.2.2.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading5;

builder.Writeln("Heading 1.2.2.2.1");
builder.Writeln("Heading 1.2.2.2.2");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "PdfSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi .PDF'ye dönüştürme şeklini değiştirmek için.
PdfSaveOptions options = new PdfSaveOptions();

// Çıktı PDF belgesi, belge gövdesindeki başlıkları listeleyen bir içindekiler tablosu olan bir anahat içerecektir.
// Bu taslakta bir girdiye tıklamak bizi ilgili başlığın konumuna götürecektir.
// Seviyeleri 4'ün üzerinde olan tüm başlıkları anahattan çıkarmak için "HeadingsOutlineLevels" özelliğini "4" olarak ayarlayın.
options.OutlineOptions.HeadingsOutlineLevels = 4;

// Bir anahat girişinin kendisi ile aynı veya daha düşük seviyedeki bir sonraki giriş arasında daha yüksek bir seviyenin müteakip girişleri varsa,
// girişin solunda bir ok görünecek. Bu girdi, bu tür birkaç "alt girdinin" "sahibidir".
// Belgemizde, 5. başlık seviyesindeki anahat girişleri, ikinci 4. seviye anahat girişinin alt girdileridir,
 // 4. ve 5. başlık seviyesi girişleri, ikinci 3. seviye girişinin alt girişleridir ve bu şekilde devam eder.
// Anahatta, tüm alt girişlerini daraltmak/genişletmek için "sahip" girişinin okuna tıklayabiliriz.
// Tüm başlık düzeyi 2 ve alt anahat girişlerini otomatik olarak genişletmek için "ExpandedOutlineLevels" özelliğini "2" olarak ayarlayın
 // ve belgeyi açtığımızda tüm seviye ve 3 ve üzeri girişleri daralt.
options.OutlineOptions.ExpandedOutlineLevels = 2;

doc.Save(ArtifactsDir + "PdfSaveOptions.ExpandedOutlineLevels.pdf", options);
```

### Ayrıca bakınız

* class [OutlineOptions](../)
* ad alanı [Aspose.Words.Saving](../../outlineoptions/)
* toplantı [Aspose.Words](../../../)


