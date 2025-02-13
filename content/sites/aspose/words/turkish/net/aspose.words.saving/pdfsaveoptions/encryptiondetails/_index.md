---
title: PdfSaveOptions.EncryptionDetails
second_title: Aspose.Words for .NET API Referansı
description: PdfSaveOptions mülk. Çıktı PDF belgesini şifrelemek için ayrıntıları alır veya ayarlar.
type: docs
weight: 110
url: /tr/net/aspose.words.saving/pdfsaveoptions/encryptiondetails/
---
## PdfSaveOptions.EncryptionDetails property

Çıktı PDF belgesini şifrelemek için ayrıntıları alır veya ayarlar.

```csharp
public PdfEncryptionDetails EncryptionDetails { get; set; }
```

### Notlar

Varsayılan değer null ve çıktı belgesi şifrelenmeyecek. Bu özellik geçerli bir değere ayarlandığında[`PdfEncryptionDetails`](../../pdfencryptiondetails/) object, sonra çıktı PDF belgesi şifrelenecektir.

PDF 1.7 tabanlı uyumluluğa kaydederken AES-128 şifreleme algoritması kullanılır (PDF/UA-1 dahil). PDF 2.0 tabanlı uyumluluğa kaydederken AES-256 şifreleme algoritması kullanılır.

Şifreleme, PDF/A uyumluluğu tarafından yasaklanmıştır. Bu seçenek, PDF/A'ya kaydedilirken yok sayılacaktır.

ContentCopyForAccessibilityçıktı belgesi şifrelenmişse PDF/UA Compliance tarafından izin gerekir. Bu izin, PDF/UA'ya kaydederken otomatik olarak kullanılacaktır.

ContentCopyForAccessibility izin, PDF 2.0 biçiminde kullanımdan kaldırılmıştır. Bu izin, PDF 2.0'a kaydedilirken yok sayılacaktır.

### Örnekler

Kaydedilmiş bir PDF belgesinde izinlerin nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");

PdfEncryptionDetails encryptionDetails =
    new PdfEncryptionDetails("password", string.Empty);

// Tüm izinleri reddederek başlayın.
encryptionDetails.Permissions = PdfPermissions.DisallowAll;

// Ek açıklamaların düzenlenmesine izin vermek için izinleri genişletin.
encryptionDetails.Permissions = PdfPermissions.ModifyAnnotations | PdfPermissions.DocumentAssembly;

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "PdfSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi .PDF'ye dönüştürme şeklini değiştirmek için.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// "EncryptionDetails" özelliği ile şifrelemeyi etkinleştirin.
saveOptions.EncryptionDetails = encryptionDetails;

// Bu belgeyi açtığımızda, içeriğine erişmeden önce şifreyi sağlamamız gerekecek.
doc.Save(ArtifactsDir + "PdfSaveOptions.EncryptionPermissions.pdf", saveOptions);
```

### Ayrıca bakınız

* class [PdfEncryptionDetails](../../pdfencryptiondetails/)
* class [PdfSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../pdfsaveoptions/)
* toplantı [Aspose.Words](../../../)


