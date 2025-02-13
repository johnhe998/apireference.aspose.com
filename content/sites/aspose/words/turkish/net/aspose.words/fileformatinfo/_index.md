---
title: Class FileFormatInfo
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.FileFormatInfo sınıf. Tarafından döndürülen verileri içerirFileFormatUtil belge biçimi algılama yöntemleri.
type: docs
weight: 2630
url: /tr/net/aspose.words/fileformatinfo/
---
## FileFormatInfo class

Tarafından döndürülen verileri içerir[`FileFormatUtil`](../fileformatutil/) belge biçimi algılama yöntemleri.

```csharp
public class FileFormatInfo
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [Encoding](../../aspose.words/fileformatinfo/encoding/) { get; } | Geçerli belge biçimi için geçerliyse algılanan kodlamayı alır. Şu anda yalnızca HTML belgeleri için kodlamayı algılar. |
| [HasDigitalSignature](../../aspose.words/fileformatinfo/hasdigitalsignature/) { get; } | Bu belge bir dijital imza içeriyorsa true değerini döndürür. Bu özellik, yalnızca belgesinde bir dijital imzanın bulunduğunu bildirir, ancak imzanın geçerli olup olmadığını belirtmez. |
| [IsEncrypted](../../aspose.words/fileformatinfo/isencrypted/) { get; } | Belge şifrelenmişse ve açmak için bir parola gerektiriyorsa true değerini döndürür. |
| [LoadFormat](../../aspose.words/fileformatinfo/loadformat/) { get; } | Algılanan belge biçimini alır. |

### Notlar

Bu sınıfın örneklerini doğrudan oluşturmazsınız. Bu sınıfın nesneleri tarafından döndürülür[`DetectFileFormat`](../fileformatutil/detectfileformat/)yöntemler.

### Örnekler

Belge biçimini ve şifrelemeyi algılamak için FileFormatUtil sınıfının nasıl kullanılacağını gösterir.

```csharp
Document doc = new Document();

// Belgeyi şifrelemek için bir SaveOptions nesnesi yapılandırın
// kaydettiğimizde bir şifre ile ve ardından belgeyi kaydedin.
OdtSaveOptions saveOptions = new OdtSaveOptions(SaveFormat.Odt);
saveOptions.Password = "MyPassword";

doc.Save(ArtifactsDir + "File.DetectDocumentEncryption.odt", saveOptions);

// Belgemizin dosya türünü ve şifreleme durumunu doğrulayın.
FileFormatInfo info = FileFormatUtil.DetectFileFormat(ArtifactsDir + "File.DetectDocumentEncryption.odt");

Assert.AreEqual(".odt", FileFormatUtil.LoadFormatToExtension(info.LoadFormat));
Assert.True(info.IsEncrypted);
```

Belge biçimini ve dijital imzaların varlığını algılamak için FileFormatUtil sınıfının nasıl kullanılacağını gösterir.

```csharp
// Belgenin dijital olarak imzalanmadığını doğrulamak için bir FileFormatInfo örneği kullanın.
FileFormatInfo info = FileFormatUtil.DetectFileFormat(MyDir + "Document.docx");

Assert.AreEqual(".docx", FileFormatUtil.LoadFormatToExtension(info.LoadFormat));
Assert.False(info.HasDigitalSignature);

CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw", null);
DigitalSignatureUtil.Sign(MyDir + "Document.docx", ArtifactsDir + "File.DetectDigitalSignatures.docx",
    certificateHolder, new SignOptions() { SignTime = DateTime.Now });

// İmzalandığını doğrulamak için yeni bir FileFormatInstance kullanın.
info = FileFormatUtil.DetectFileFormat(ArtifactsDir + "File.DetectDigitalSignatures.docx");

Assert.True(info.HasDigitalSignature);

// Böyle bir koleksiyonda imzalanmış bir belgenin imzalarını yükleyebilir ve erişebiliriz.
Assert.AreEqual(1, DigitalSignatureUtil.LoadSignatures(ArtifactsDir + "File.DetectDigitalSignatures.docx").Count);
```

### Ayrıca bakınız

* ad alanı [Aspose.Words](../../aspose.words/)
* toplantı [Aspose.Words](../../)


