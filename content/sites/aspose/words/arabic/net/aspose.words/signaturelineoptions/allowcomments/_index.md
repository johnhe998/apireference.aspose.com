---
title: SignatureLineOptions.AllowComments
second_title: Aspose.Words لمراجع .NET API
description: SignatureLineOptions ملكية. الحصول على أو تعيين قيمة تشير إلى أن الموقّع يمكنه إضافة تعليقات في مربع حوار التوقيع . القيمة الافتراضية لهذه الخاصية هي خاطئة .
type: docs
weight: 20
url: /ar/net/aspose.words/signaturelineoptions/allowcomments/
---
## SignatureLineOptions.AllowComments property

الحصول على أو تعيين قيمة تشير إلى أن الموقّع يمكنه إضافة تعليقات في مربع حوار التوقيع . القيمة الافتراضية لهذه الخاصية هي **خاطئة** .

```csharp
public bool AllowComments { get; set; }
```

### أمثلة

يوضح كيفية توقيع مستند بشهادة شخصية وسطر توقيع.

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

// أعد فتح المستند المحفوظ ، وتحقق من أن خصائص "IsSigned" و "IsValid" تساوي "true" ،
// يشير إلى أن سطر التوقيع يحتوي على توقيع.
doc = new Document(ArtifactsDir + "DocumentBuilder.SignatureLineProviderId.Signed.docx");
Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);
signatureLine = shape.SignatureLine;

Assert.True(signatureLine.IsSigned);
Assert.True(signatureLine.IsValid);
```

### أنظر أيضا

* class [SignatureLineOptions](../)
* مساحة الاسم [Aspose.Words](../../signaturelineoptions/)
* المجسم [Aspose.Words](../../../)


