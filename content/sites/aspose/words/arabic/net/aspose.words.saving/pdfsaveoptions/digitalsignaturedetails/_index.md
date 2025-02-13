---
title: PdfSaveOptions.DigitalSignatureDetails
second_title: Aspose.Words لمراجع .NET API
description: PdfSaveOptions ملكية. الحصول على أو تعيين التفاصيل الخاصة بتوقيع مستند PDF الناتج.
type: docs
weight: 60
url: /ar/net/aspose.words.saving/pdfsaveoptions/digitalsignaturedetails/
---
## PdfSaveOptions.DigitalSignatureDetails property

الحصول على أو تعيين التفاصيل الخاصة بتوقيع مستند PDF الناتج.

```csharp
public PdfDigitalSignatureDetails DigitalSignatureDetails { get; set; }
```

### ملاحظات

القيمة الافتراضية خالية ولن يتم توقيع مستند الإخراج . عند تعيين هذه الخاصية على صالحة[`PdfDigitalSignatureDetails`](../../pdfdigitalsignaturedetails/) كائن ، ثم سيتم توقيع مستند PDF الناتج رقميًا.

### أمثلة

يوضح كيفية التوقيع على مستند PDF تم إنشاؤه.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Contents of signed PDF.");

CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
PdfSaveOptions options = new PdfSaveOptions();

// تكوين كائن "DigitalSignatureDetails" من كائن "SaveOptions" إليه
// قم بالتوقيع رقميًا على المستند كما نعرضه بطريقة "حفظ".
DateTime signingTime = DateTime.Now;
options.DigitalSignatureDetails =
    new PdfDigitalSignatureDetails(certificateHolder, "Test Signing", "My Office", signingTime);
options.DigitalSignatureDetails.HashAlgorithm = PdfDigitalSignatureHashAlgorithm.Sha256;

Assert.AreEqual("Test Signing", options.DigitalSignatureDetails.Reason);
Assert.AreEqual("My Office", options.DigitalSignatureDetails.Location);
Assert.AreEqual(signingTime.ToUniversalTime(), options.DigitalSignatureDetails.SignatureDate.ToUniversalTime());

doc.Save(ArtifactsDir + "PdfSaveOptions.PdfDigitalSignature.pdf", options);
```

### أنظر أيضا

* class [PdfDigitalSignatureDetails](../../pdfdigitalsignaturedetails/)
* class [PdfSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../pdfsaveoptions/)
* المجسم [Aspose.Words](../../../)


