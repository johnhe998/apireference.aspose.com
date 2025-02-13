---
title: Class DigitalSignatureUtil
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.DigitalSignatures.DigitalSignatureUtil sınıf. Belgeyi imzalamak için yöntemler sağlar.
type: docs
weight: 400
url: /tr/net/aspose.words.digitalsignatures/digitalsignatureutil/
---
## DigitalSignatureUtil class

Belgeyi imzalamak için yöntemler sağlar.

```csharp
public static class DigitalSignatureUtil
```

## yöntemler

| İsim | Tanım |
| --- | --- |
| static [LoadSignatures](../../aspose.words.digitalsignatures/digitalsignatureutil/loadsignatures/#loadsignatures)(Stream) | Akış kullanarak belgeden dijital imzaları yükler. |
| static [LoadSignatures](../../aspose.words.digitalsignatures/digitalsignatureutil/loadsignatures/#loadsignatures_1)(string) | Belgeden dijital imzaları yükler. |
| static [RemoveAllSignatures](../../aspose.words.digitalsignatures/digitalsignatureutil/removeallsignatures/#removeallsignatures)(Stream, Stream) | Kaynak akıştaki belgedeki tüm dijital imzaları kaldırır ve imzasız belgeyi hedef akışa yazar. |
| static [RemoveAllSignatures](../../aspose.words.digitalsignatures/digitalsignatureutil/removeallsignatures/#removeallsignatures_1)(string, string) | Tüm dijital imzaları kaynak dosyadan kaldırır ve imzasız dosyayı hedef dosyaya yazar. |
| static [Sign](../../aspose.words.digitalsignatures/digitalsignatureutil/sign/#sign)(Stream, Stream, CertificateHolder) | Verilenleri kullanarak kaynak belgeyi imzalar[`CertificateHolder`](../certificateholder/)dijital imza ile ve imzalı belgeyi hedef akışa yazar. |
| static [Sign](../../aspose.words.digitalsignatures/digitalsignatureutil/sign/#sign_2)(string, string, CertificateHolder) | Verilenleri kullanarak kaynak belgeyi imzalar[`CertificateHolder`](../certificateholder/) dijital imza ile ve imzalı belgeyi hedef dosyaya yazar. |
| static [Sign](../../aspose.words.digitalsignatures/digitalsignatureutil/sign/#sign_1)(Stream, Stream, CertificateHolder, SignOptions) | Verilenleri kullanarak kaynak belgeyi imzalar[`CertificateHolder`](../certificateholder/) ve[`SignOptions`](../signoptions/) dijital imzalı ve imzalı belgeyi hedef akışa yazar. |
| static [Sign](../../aspose.words.digitalsignatures/digitalsignatureutil/sign/#sign_3)(string, string, CertificateHolder, SignOptions) | Verilenleri kullanarak kaynak belgeyi imzalar[`CertificateHolder`](../certificateholder/) ve[`SignOptions`](../signoptions/) dijital imzalı ve imzalı belgeyi hedef dosyaya yazar. |

### Notlar

Sayısal imza, Belge Nesne Modeli yerine dosya içeriği ile çalıştığı için bu yöntemler ayrı bir sınıfa alınır.

Desteklenen biçimlerDoc veDocx.

### Örnekler

Dijital olarak imzalanmış bir belgeden imzaların nasıl yükleneceğini gösterir.

```csharp
// İmzalı bir belgenin dijital imza koleksiyonunu DigitalSignatureUtil sınıfını kullanarak yüklemenin iki yolu vardır.
// 1 - Yerel dosya sistemi dosya adından bir belgeden yükleyin:
DigitalSignatureCollection digitalSignatures = 
    DigitalSignatureUtil.LoadSignatures(MyDir + "Digitally signed.docx");

// Bu koleksiyon boş değilse, belgenin dijital olarak imzalandığını doğrulayabiliriz.
Assert.AreEqual(1, digitalSignatures.Count);

// 2 - FileStream'den bir belgeden yükleyin:
using (Stream stream = new FileStream(MyDir + "Digitally signed.docx", FileMode.Open))
{
    digitalSignatures = DigitalSignatureUtil.LoadSignatures(stream);
    Assert.AreEqual(1, digitalSignatures.Count);
}
```

Dijital olarak imzalanmış bir belgeden dijital imzaların nasıl kaldırılacağını gösterir.

```csharp
// Dijital imzaları kaldırmak için DigitalSignatureUtil sınıfını kullanmanın iki yolu vardır.
// imzasız bir kopyasını yerel dosya sisteminde başka bir yere kaydederek imzalı bir belgeden.
// 1 - Dosya adı dizelerine göre hem imzalı belgenin hem de imzasız kopyanın konumlarını belirleyin:
DigitalSignatureUtil.RemoveAllSignatures(MyDir + "Digitally signed.docx",
    ArtifactsDir + "DigitalSignatureUtil.LoadAndRemove.FromString.docx");

// 2 - Dosya akışlarına göre hem imzalı belgenin hem de imzasız kopyanın konumlarını belirleyin:
using (Stream streamIn = new FileStream(MyDir + "Digitally signed.docx", FileMode.Open))
{
    using (Stream streamOut = new FileStream(ArtifactsDir + "DigitalSignatureUtil.LoadAndRemove.FromStream.docx", FileMode.Create))
    {
        DigitalSignatureUtil.RemoveAllSignatures(streamIn, streamOut);
    }
}

// Her iki çıktı belgemizin de dijital imzası olmadığını doğrulayın.
Assert.That(DigitalSignatureUtil.LoadSignatures(ArtifactsDir + "DigitalSignatureUtil.LoadAndRemove.FromString.docx"), Is.Empty);
Assert.That(DigitalSignatureUtil.LoadSignatures(ArtifactsDir + "DigitalSignatureUtil.LoadAndRemove.FromStream.docx"), Is.Empty);
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.DigitalSignatures](../../aspose.words.digitalsignatures/)
* toplantı [Aspose.Words](../../)


