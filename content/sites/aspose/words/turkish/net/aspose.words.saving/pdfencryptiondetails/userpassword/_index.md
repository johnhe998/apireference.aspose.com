---
title: PdfEncryptionDetails.UserPassword
second_title: Aspose.Words for .NET API Referansı
description: PdfEncryptionDetails mülk. Şifrelenmiş PDF belgesini açmak için gereken kullanıcı parolasını belirtir.
type: docs
weight: 40
url: /tr/net/aspose.words.saving/pdfencryptiondetails/userpassword/
---
## PdfEncryptionDetails.UserPassword property

Şifrelenmiş PDF belgesini açmak için gereken kullanıcı parolasını belirtir.

```csharp
public string UserPassword { get; set; }
```

### Notlar

Görüntülemek üzere şifrelenmiş bir PDF belgesini açmak için kullanıcı şifresi gerekecektir. içinde belirtilen izinler[`Permissions`](../permissions/) okuyucu yazılımı tarafından uygulanacaktır.

Kullanıcı parolası boş veya boş dize olabilir, bu durumda PDF belgesini açarken kullanıcıdan parola istenmeyecektir. Kullanıcı parolası, sahip parolasıyla aynı olamaz.

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


