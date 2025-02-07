---
title: LoadOptions.Password
second_title: Aspose.Words for .NET API Referansı
description: LoadOptions mülk. Şifrelenmiş bir belgeyi açmak için parolayı alır veya ayarlar. Boş veya boş dize olabilir. Varsayılan null.
type: docs
weight: 110
url: /tr/net/aspose.words.loading/loadoptions/password/
---
## LoadOptions.Password property

Şifrelenmiş bir belgeyi açmak için parolayı alır veya ayarlar. Boş veya boş dize olabilir. Varsayılan null.

```csharp
public string Password { get; set; }
```

### Notlar

Şifrelenmiş bir belgeyi açmak için şifreyi bilmeniz gerekir. Belge şifrelenmemişse, bunu boş veya boş dizeye ayarlayın.

### Örnekler

Şifreli belge dosyasının nasıl imzalanacağını gösterir.

```csharp
// PKCS#12 deposundan özel anahtar içermesi gereken bir X.509 sertifikası oluşturun.
CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

// Yeni dijital imzamızla uygulanacak bir yorum, tarih ve şifre çözme şifresi oluşturun.
SignOptions signOptions = new SignOptions
{
    Comments = "Comment",
    SignTime = DateTime.Now,
    DecryptionPassword = "docPassword"
};

// İmzasız giriş belgesi için yerel bir sistem dosya adı ve dijital olarak imzalanmış yeni kopyası için bir çıkış dosya adı ayarlayın.
string inputFileName = MyDir + "Encrypted.docx";
string outputFileName = ArtifactsDir + "DigitalSignatureUtil.DecryptionPassword.docx";

DigitalSignatureUtil.Sign(inputFileName, outputFileName, certificateHolder, signOptions);
```

### Ayrıca bakınız

* class [LoadOptions](../)
* ad alanı [Aspose.Words.Loading](../../loadoptions/)
* toplantı [Aspose.Words](../../../)


