---
title: PdfDigitalSignatureDetails.Reason
second_title: Aspose.Words for .NET API 参考
description: PdfDigitalSignatureDetails 财产. 获取或设置签名的原因
type: docs
weight: 50
url: /zh/net/aspose.words.saving/pdfdigitalsignaturedetails/reason/
---
## PdfDigitalSignatureDetails.Reason property

获取或设置签名的原因。

```csharp
public string Reason { get; set; }
```

### 评论

默认值为空。

### 例子

显示如何签署生成的 PDF 文档。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Contents of signed PDF.");

CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

// 创建一个“PdfSaveOptions”对象，我们可以将它传递给文档的“Save”方法
// 修改该方法如何将文档转换为 .PDF。
PdfSaveOptions options = new PdfSaveOptions();

// 将“SaveOptions”对象的“DigitalSignatureDetails”对象配置为
// 在我们使用“Save”方法渲染文档时对文档进行数字签名。
DateTime signingTime = DateTime.Now;
options.DigitalSignatureDetails =
    new PdfDigitalSignatureDetails(certificateHolder, "Test Signing", "My Office", signingTime);
options.DigitalSignatureDetails.HashAlgorithm = PdfDigitalSignatureHashAlgorithm.Sha256;

Assert.AreEqual("Test Signing", options.DigitalSignatureDetails.Reason);
Assert.AreEqual("My Office", options.DigitalSignatureDetails.Location);
Assert.AreEqual(signingTime.ToUniversalTime(), options.DigitalSignatureDetails.SignatureDate.ToUniversalTime());

doc.Save(ArtifactsDir + "PdfSaveOptions.PdfDigitalSignature.pdf", options);
```

### 也可以看看

* class [PdfDigitalSignatureDetails](../)
* 命名空间 [Aspose.Words.Saving](../../pdfdigitalsignaturedetails/)
* 部件 [Aspose.Words](../../../)


