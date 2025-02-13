---
title: PdfSaveOptions.ImageColorSpaceExportMode
second_title: Aspose.Words for .NET API Referansı
description: PdfSaveOptions mülk. PDF belgesindeki resimler için renk uzayının nasıl seçileceğini belirtir.
type: docs
weight: 160
url: /tr/net/aspose.words.saving/pdfsaveoptions/imagecolorspaceexportmode/
---
## PdfSaveOptions.ImageColorSpaceExportMode property

PDF belgesindeki resimler için renk uzayının nasıl seçileceğini belirtir.

```csharp
public PdfImageColorSpaceExportMode ImageColorSpaceExportMode { get; set; }
```

### Notlar

Varsayılan değerAuto .

EğerSimpleCmyk değer belirtildi, [`ImageCompression`](../imagecompression/) seçenek yoksayılır ve Belgedeki tüm görüntüler için düz sıkıştırma kullanılır.

SimpleCmyk değer, PDF/A'ya kaydedilirken desteklenmiyor. Auto Bunun yerine değer kullanılacaktır.

### Örnekler

PDF'ye dışa aktarırken bir belgedeki görüntüler için nasıl farklı bir renk uzayı ayarlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Jpeg image:");
builder.InsertImage(ImageDir + "Logo.jpg");
builder.InsertParagraph();
builder.Writeln("Png image:");
builder.InsertImage(ImageDir + "Transparent background logo.png");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "PdfSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi .PDF'ye dönüştürme şeklini değiştirmek için.
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();

// Aspose.Words'ü almak için "ImageColorSpaceExportMode" özelliğini "PdfImageColorSpaceExportMode.Auto" olarak ayarlayın
// PDF'ye dönüştürdüğü belgedeki resimler için renk uzayını otomatik olarak seç.
// Çoğu durumda renk uzayı RGB olacaktır.
// "ImageColorSpaceExportMode" özelliğini "PdfImageColorSpaceExportMode.SimpleCmyk" olarak ayarlayın
// kaydedilen PDF'deki tüm resimler için CMYK renk alanını kullanmak için.
// Aspose.Words ayrıca tüm görüntülere Flate sıkıştırması uygulayacak ve "ImageCompression" özelliğinin değerini yok sayacaktır.
pdfSaveOptions.ImageColorSpaceExportMode = pdfImageColorSpaceExportMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.ImageColorSpaceExportMode.pdf", pdfSaveOptions);
```

### Ayrıca bakınız

* enum [PdfImageColorSpaceExportMode](../../pdfimagecolorspaceexportmode/)
* class [PdfSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../pdfsaveoptions/)
* toplantı [Aspose.Words](../../../)


