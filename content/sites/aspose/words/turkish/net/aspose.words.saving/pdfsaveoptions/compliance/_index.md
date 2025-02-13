---
title: PdfSaveOptions.Compliance
second_title: Aspose.Words for .NET API Referansı
description: PdfSaveOptions mülk. Çıktı belgeleri için PDF standartları uyumluluk düzeyini belirtir.
type: docs
weight: 30
url: /tr/net/aspose.words.saving/pdfsaveoptions/compliance/
---
## PdfSaveOptions.Compliance property

Çıktı belgeleri için PDF standartları uyumluluk düzeyini belirtir.

```csharp
public PdfCompliance Compliance { get; set; }
```

### Notlar

VarsayılanPdf17.

### Örnekler

Kaydedilmiş PDF belgelerinin PDF standartlarına uygunluk düzeyinin nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "PdfSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi .PDF'ye dönüştürme şeklini değiştirmek için.
// Bazı PdfSaveOptions'ın standartlardan birine kaydedilirken yasaklandığını ve otomatik olarak düzeltildiğini unutmayın.
// Hangi seçeneklerin otomatik olarak düzeltildiğini öğrenmek için IWarningCallback'i kullanın.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// "PDF/A-1b" standardına uymak için "Compliance" özelliğini "PdfCompliance.PdfA1b" olarak ayarlayın,
// Aspose.Words onu PDF'ye dönüştürürken belgenin görsel görünümünü korumayı amaçlar.
// "1.7" standardına uymak için "Uyum" özelliğini "PdfCompliance.Pdf17" olarak ayarlayın.
// "PDF/A-1a" standardına uymak için "Compliance" özelliğini "PdfCompliance.PdfA1a" olarak ayarlayın,
// "PDF/A-1b" ile uyumludur ve orijinal belgenin belge yapısını korur.
// "PDF/UA-1" (ISO 14289-1) standardına uymak için "Uyum" özelliğini "PdfCompliance.PdfUa1" olarak ayarlayın,
// dosyanın erişilebilir olmasını sağlayan elektronik belgeleri PDF olarak temsil etmeyi tanımlamayı amaçlar.
// Bu, belgelerin aranabilir olmasına yardımcı olur, ancak zaten büyük olan belgelerin boyutunu önemli ölçüde artırabilir.
saveOptions.Compliance = pdfCompliance;

doc.Save(ArtifactsDir + "PdfSaveOptions.Compliance.pdf", saveOptions);
```

### Ayrıca bakınız

* enum [PdfCompliance](../../pdfcompliance/)
* class [PdfSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../pdfsaveoptions/)
* toplantı [Aspose.Words](../../../)


