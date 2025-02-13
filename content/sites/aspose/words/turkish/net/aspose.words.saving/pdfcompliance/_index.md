---
title: Enum PdfCompliance
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Saving.PdfCompliance Sıralama. PDF standartları uyumluluk düzeyini belirtir.
type: docs
weight: 5130
url: /tr/net/aspose.words.saving/pdfcompliance/
---
## PdfCompliance enumeration

PDF standartları uyumluluk düzeyini belirtir.

```csharp
public enum PdfCompliance
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| Pdf17 | `0` | Çıktı dosyası, PDF 1.7 (ISO 32000-1) standardına uygun olacaktır. |
| Pdf20 | `1` | Çıktı dosyası, PDF 2.0 (ISO 32000-2) standardına uygun olacaktır. |
| PdfA1a | `2` | Çıktı dosyası, PDF/A-1a (ISO 19005-1) standardına uygun olacaktır. Bu düzey, PDF/A-1b'nin tüm gereksinimlerini içerir ve ayrıca, belge yapısının dahil edilmesini gerektirir ("etiketli" olarak da bilinir) ), belge içeriğinin aranabilmesini ve başka bir amaca uygun hale getirilebilmesini sağlamak amacıyla. |
| PdfA1b | `3` | Çıktı dosyası, PDF/A-1b (ISO 19005-1) standardına uygun olacaktır. PDF/A-1b, belgenin görsel görünümünün güvenilir şekilde çoğaltılmasını sağlama amacına sahiptir. |
| PdfA2a | `4` | Çıktı dosyası, PDF/A-2a (ISO 19005-2) standardına uygun olacaktır. Bu düzey, PDF/A-2u'nun tüm gereksinimlerini içerir ve ayrıca, belge yapısının dahil edilmesini gerektirir ("etiketli" olarak da bilinir) ), belge içeriğinin aranabilmesini ve başka bir amaca uygun hale getirilebilmesini sağlamak amacıyla. |
| PdfA2u | `5` | Çıktı dosyası, PDF/A-2u (ISO 19005-2) standardına uygun olacaktır. PDF/A-2u, araçlar ve oluşturma, depolama için kullanılan sistemlerden bağımsız olarak, zaman içinde belge statik görsel görünümünü koruma amacına sahiptir. veya dosyaların işlenmesi. Ayrıca, document içinde bulunan herhangi bir metin, bir dizi Unicode kod noktası olarak güvenilir bir şekilde çıkarılabilir. |
| PdfA4 | `6` | Çıktı dosyası, PDF/A-4 (ISO 19005-4:2020) standardına uygun olacaktır. PDF/A-4, araçlar ve oluşturmak için kullanılan sistemlerden bağımsız olarak, zaman içinde belgenin statik görsel görünümünü koruma amacına sahiptir. , dosyaları depolamak veya işlemek. Ayrıca, document içinde bulunan herhangi bir metin, bir dizi Unicode kod noktası olarak güvenilir bir şekilde çıkarılabilir. |
| PdfUa1 | `7` | Çıktı dosyası, PDF/UA-1 (ISO 14289-1) standardına uygun olacaktır. PDF/UA'nın birincil amacı, elektronik belgelerin, dosyanın erişilebilir. |

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

* ad alanı [Aspose.Words.Saving](../../aspose.words.saving/)
* toplantı [Aspose.Words](../../)


