---
title: SignOptions.DecryptionPassword
second_title: Aspose.Words for .NET API Referansı
description: SignOptions mülk. Kaynak belgenin şifresini çözmek için parola. Varsayılan değer boş dize Empty .
type: docs
weight: 30
url: /tr/net/aspose.words.digitalsignatures/signoptions/decryptionpassword/
---
## SignOptions.DecryptionPassword property

Kaynak belgenin şifresini çözmek için parola. Varsayılan değer **boş dize** (Empty ).

```csharp
public string DecryptionPassword { get; set; }
```

### Notlar

OOXML belgesi şifrelenmişse, imzalanmadan önce kaynak belgenin şifresini çözmek için şifre çözme password sağlamanız gerekir. Bu, ikili DOC biçimindeki belgeler için gerekli değildir.

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

* class [SignOptions](../)
* ad alanı [Aspose.Words.DigitalSignatures](../../signoptions/)
* toplantı [Aspose.Words](../../../)


