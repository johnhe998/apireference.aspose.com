---
title: PdfEncryptionDetails.Permissions
second_title: Aspose.Words for .NET API Referansı
description: PdfEncryptionDetails mülk. Şifrelenmiş bir PDF belgesinde bir kullanıcıya izin verilen işlemleri belirtir. Varsayılan değerDisallowAll .
type: docs
weight: 30
url: /tr/net/aspose.words.saving/pdfencryptiondetails/permissions/
---
## PdfEncryptionDetails.Permissions property

Şifrelenmiş bir PDF belgesinde bir kullanıcıya izin verilen işlemleri belirtir. Varsayılan değerDisallowAll .

```csharp
public PdfPermissions Permissions { get; set; }
```

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

* enum [PdfPermissions](../../pdfpermissions/)
* class [PdfEncryptionDetails](../)
* ad alanı [Aspose.Words.Saving](../../pdfencryptiondetails/)
* toplantı [Aspose.Words](../../../)


