---
title: SignatureLineOptions.DefaultInstructions
second_title: Aspose.Words for .NET API 参考
description: SignatureLineOptions 财产. 获取或设置一个值指示默认指令显示在签名对话框中 此属性的默认值为 真的.
type: docs
weight: 30
url: /zh/net/aspose.words/signaturelineoptions/defaultinstructions/
---
## SignatureLineOptions.DefaultInstructions property

获取或设置一个值，指示默认指令显示在签名对话框中。 此属性的默认值为 **真的**.

```csharp
public bool DefaultInstructions { get; set; }
```

### 例子

显示如何使用个人证书和签名行签署文档。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
    Signer = "vderyushev",
    SignerTitle = "QA",
    Email = "vderyushev@aspose.com",
    ShowDate = true,
    DefaultInstructions = false,
    Instructions = "Please sign here.",
    AllowComments = true
};

SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");

Assert.False(signatureLine.IsSigned);
Assert.False(signatureLine.IsValid);

doc.Save(ArtifactsDir + "DocumentBuilder.SignatureLineProviderId.docx");

SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    ProviderId = signatureLine.ProviderId,
    Comments = "Document was signed by vderyushev",
    SignTime = DateTime.Now
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(ArtifactsDir + "DocumentBuilder.SignatureLineProviderId.docx", 
    ArtifactsDir + "DocumentBuilder.SignatureLineProviderId.Signed.docx", certHolder, signOptions);

// 重新打开我们保存的文档，并验证 "IsSigned" 和 "IsValid" 属性都等于 "true",
// 表示签名行包含签名。
doc = new Document(ArtifactsDir + "DocumentBuilder.SignatureLineProviderId.Signed.docx");
Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);
signatureLine = shape.SignatureLine;

Assert.True(signatureLine.IsSigned);
Assert.True(signatureLine.IsValid);
```

### 也可以看看

* class [SignatureLineOptions](../)
* 命名空间 [Aspose.Words](../../signaturelineoptions/)
* 部件 [Aspose.Words](../../../)


