---
title: PdfEncryptionDetails.OwnerPassword
second_title: Aspose.Words for .NET API Referansı
description: PdfEncryptionDetails mülk. Şifrelenmiş PDF belgesi için sahip parolasını belirtir.
type: docs
weight: 20
url: /tr/net/aspose.words.saving/pdfencryptiondetails/ownerpassword/
---
## PdfEncryptionDetails.OwnerPassword property

Şifrelenmiş PDF belgesi için sahip parolasını belirtir.

```csharp
public string OwnerPassword { get; set; }
```

### Notlar

Sahip parolası, kullanıcının, içinde belirtilen herhangi bir erişim kısıtlaması olmadan şifreli bir PDF belgesi açmasına izin verir.[`Permissions`](../permissions/).

Sahip parolası, kullanıcı parolası ile aynı olamaz.

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

* class [PdfEncryptionDetails](../)
* ad alanı [Aspose.Words.Saving](../../pdfencryptiondetails/)
* toplantı [Aspose.Words](../../../)


