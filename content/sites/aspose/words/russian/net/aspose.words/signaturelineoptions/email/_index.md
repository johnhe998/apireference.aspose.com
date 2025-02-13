---
title: SignatureLineOptions.Email
second_title: Справочник по API Aspose.Words для .NET
description: SignatureLineOptions свойство. Получает или задает предполагаемый адрес электронной почты подписывающей стороны. Значение по умолчанию для этого свойства пустой строки Empty .
type: docs
weight: 40
url: /ru/net/aspose.words/signaturelineoptions/email/
---
## SignatureLineOptions.Email property

Получает или задает предполагаемый адрес электронной почты подписывающей стороны. Значение по умолчанию для этого свойства: **пустой строки** (Empty ).

```csharp
public string Email { get; set; }
```

### Примеры

Показывает, как подписать документ личным сертификатом и строкой подписи.

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

// Снова открываем наш сохраненный документ и проверяем, что свойства «IsSigned» и «IsValid» равны «true»,
// указание на то, что строка подписи содержит подпись.
doc = new Document(ArtifactsDir + "DocumentBuilder.SignatureLineProviderId.Signed.docx");
Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);
signatureLine = shape.SignatureLine;

Assert.True(signatureLine.IsSigned);
Assert.True(signatureLine.IsValid);
```

### Смотрите также

* class [SignatureLineOptions](../)
* пространство имен [Aspose.Words](../../signaturelineoptions/)
* сборка [Aspose.Words](../../../)


