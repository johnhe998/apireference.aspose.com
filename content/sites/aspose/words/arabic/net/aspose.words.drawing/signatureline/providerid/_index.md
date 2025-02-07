---
title: SignatureLine.ProviderId
second_title: Aspose.Words لمراجع .NET API
description: SignatureLine ملكية. الحصول على أو تعيين معرف موفر التوقيع لسطر التوقيع هذا . القيمة الافتراضية هي 00000000000000000000000000000000 .
type: docs
weight: 80
url: /ar/net/aspose.words.drawing/signatureline/providerid/
---
## SignatureLine.ProviderId property

الحصول على أو تعيين معرف موفر التوقيع لسطر التوقيع هذا . القيمة الافتراضية هي "{00000000-0000-0000-0000-000000000000}" .

```csharp
public Guid ProviderId { get; set; }
```

### ملاحظات

موفر خدمة التشفير (CSP) عبارة عن وحدة برمجية مستقلة تقوم بالفعل بتنفيذ خوارزميات تشفير للمصادقة والتشفير والتشفير. يحتفظ MS Office بقيمة {00000000-0000-0000-0000-000000000000} بقيمة {00000000-0000-0000-000000000000} لموفر التوقيع الافتراضي الخاص به.

يجب الحصول على المعرف الفريد العمومي (GUID) الخاص بالموفر المثبت بشكل إضافي من الوثائق التي يتم شحنها مع الموفر.

بالإضافة إلى ذلك ، يتم تعداد جميع موفري التشفير المثبتين في سجل windows. يمكن العثور عليها في المسار التالي: HKLM \ SOFTWARE \ Microsoft \ Cryptography \ Defaults \ Provider. يوجد اسم مفتاح "CP Service UUID" الذي يتوافق مع GUID لموفر التوقيع.

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

* class [SignatureLine](../)
* مساحة الاسم [Aspose.Words.Drawing](../../signatureline/)
* المجسم [Aspose.Words](../../../)


