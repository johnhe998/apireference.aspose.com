---
title: SignOptions.SignTime
second_title: Aspose.Words for .NET API Referansı
description: SignOptions mülk. İmzalama tarihi. Varsayılan değer şimdiki zaman Now .
type: docs
weight: 70
url: /tr/net/aspose.words.digitalsignatures/signoptions/signtime/
---
## SignOptions.SignTime property

İmzalama tarihi. Varsayılan değer **şimdiki zaman** (Now ).

```csharp
public DateTime SignTime { get; set; }
```

### Örnekler

Belgelerin dijital olarak nasıl imzalanacağını gösterir.

```csharp
// PKCS#12 deposundan özel anahtar içermesi gereken bir X.509 sertifikası oluşturun.
CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

// Yeni dijital imzamızla uygulanacak bir yorum ve tarih oluşturun.
SignOptions signOptions = new SignOptions
{
    Comments = "My comment", 
    SignTime = DateTime.Now
};

// Dosya akışı yoluyla yerel dosya sisteminden imzasız bir belge alın,
// ardından çıktı dosyası akışının dosya adıyla belirlenen imzalı bir kopyasını oluşturun.
using (Stream streamIn = new FileStream(MyDir + "Document.docx", FileMode.Open))
{
    using (Stream streamOut = new FileStream(ArtifactsDir + "DigitalSignatureUtil.SignDocument.docx", FileMode.OpenOrCreate))
    {
        DigitalSignatureUtil.Sign(streamIn, streamOut, certificateHolder, signOptions);
    }
}
```

### Ayrıca bakınız

* class [SignOptions](../)
* ad alanı [Aspose.Words.DigitalSignatures](../../signoptions/)
* toplantı [Aspose.Words](../../../)


