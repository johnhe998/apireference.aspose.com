---
title: FileFormatInfo.HasDigitalSignature
second_title: Aspose.Words for .NET API Referansı
description: FileFormatInfo mülk. Bu belge bir dijital imza içeriyorsa true değerini döndürür. Bu özellik yalnızca belgesinde bir dijital imzanın bulunduğunu bildirir ancak imzanın geçerli olup olmadığını belirtmez.
type: docs
weight: 20
url: /tr/net/aspose.words/fileformatinfo/hasdigitalsignature/
---
## FileFormatInfo.HasDigitalSignature property

Bu belge bir dijital imza içeriyorsa true değerini döndürür. Bu özellik, yalnızca belgesinde bir dijital imzanın bulunduğunu bildirir, ancak imzanın geçerli olup olmadığını belirtmez.

```csharp
public bool HasDigitalSignature { get; }
```

### Notlar

Bu özellik, dijital olarak imzalanmış belgeleri olmayanlardan ayırmanıza yardımcı olmak için mevcuttur. Dijital olarak imzalanmış bir belgeyi değiştirmek ve kaydetmek için Aspose.Words'ü kullanırsanız, dijital imza kaybolacaktır. Bu tasarım gereğidir, çünkü bir belgenin gerçekliğini korumak için dijital bir imza vardır. Bu özelliği kullanarak dijital olarak imzalanmış belgeleri normal belgelerle aynı şekilde işlemeden önce algılayabilir ve dijital imzayı kaybetmemek için bazı önlemler alabilir, örneğin kullanıcıyı bilgilendirebilirsiniz.

### Örnekler

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

* class [FileFormatInfo](../)
* ad alanı [Aspose.Words](../../fileformatinfo/)
* toplantı [Aspose.Words](../../../)


