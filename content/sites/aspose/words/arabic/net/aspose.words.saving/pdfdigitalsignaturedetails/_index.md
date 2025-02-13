---
title: Class PdfDigitalSignatureDetails
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Saving.PdfDigitalSignatureDetails فصل. يحتوي على تفاصيل حول توقيع مستند PDF بتوقيع رقمي.
type: docs
weight: 5150
url: /ar/net/aspose.words.saving/pdfdigitalsignaturedetails/
---
## PdfDigitalSignatureDetails class

يحتوي على تفاصيل حول توقيع مستند PDF بتوقيع رقمي.

```csharp
public class PdfDigitalSignatureDetails
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [PdfDigitalSignatureDetails](pdfdigitalsignaturedetails/#constructor)() | تهيئة مثيل لهذه الفئة . |
| [PdfDigitalSignatureDetails](pdfdigitalsignaturedetails/#constructor_1)(CertificateHolder, string, string, DateTime) | تهيئة مثيل لهذه الفئة . |

## الخصائص

| اسم | وصف |
| --- | --- |
| [CertificateHolder](../../aspose.words.saving/pdfdigitalsignaturedetails/certificateholder/) { get; set; } | إرجاع كائن حامل الشهادة الذي يحتوي على الشهادة المستخدمة لتوقيع المستند. |
| [HashAlgorithm](../../aspose.words.saving/pdfdigitalsignaturedetails/hashalgorithm/) { get; set; } | الحصول على أو تعيين خوارزمية التجزئة. |
| [Location](../../aspose.words.saving/pdfdigitalsignaturedetails/location/) { get; set; } | الحصول على أو تحديد موقع التوقيع. |
| [Reason](../../aspose.words.saving/pdfdigitalsignaturedetails/reason/) { get; set; } | الحصول على أو تحديد سبب التوقيع. |
| [SignatureDate](../../aspose.words.saving/pdfdigitalsignaturedetails/signaturedate/) { get; set; } | الحصول على تاريخ التوقيع أو تحديده. |
| [TimestampSettings](../../aspose.words.saving/pdfdigitalsignaturedetails/timestampsettings/) { get; set; } | الحصول على أو تعيين إعدادات الطابع الزمني للتوقيع الرقمي. |

### ملاحظات

في الوقت الحالي ، لا يتوفر توقيع مستندات PDF رقميًا إلا على .NET 2.0 أو أعلى.

للتوقيع رقميًا على مستند PDF عند إنشائه بواسطة Aspose.Words ، قم بتعيين[`DigitalSignatureDetails`](../pdfsaveoptions/digitalsignaturedetails/) إلى صالح`PdfDigitalSignatureDetails` الكائن ثم احفظ المستند بتنسيق PDF ويمرر [`PdfSaveOptions`](../pdfsaveoptions/)كمعامل في[`Save`](../../aspose.words/document/save/) طريقة.

ينشئ Aspose.Words توقيع PKCS # 7 على مستند PDF بالكامل ويستخدم مرشح "Adobe.PPKMS" والمرشح الفرعي "adbe.pkcs7.sha1" عند إنشاء توقيع رقمي.

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

* مساحة الاسم [Aspose.Words.Saving](../../aspose.words.saving/)
* المجسم [Aspose.Words](../../)


