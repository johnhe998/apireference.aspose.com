---
title: DigitalSignatureCollection.IsValid
second_title: Aspose.Words لمراجع .NET API
description: DigitalSignatureCollection ملكية. عوائدحقيقي إذا كانت جميع التوقيعات الرقمية في هذه المجموعة صالحة ولم يتم العبث بالمستند يتم إرجاعه أيضًاحقيقيفي حالة عدم وجود توقيعات رقميةخاطئة إذا كان هناك توقيع رقمي واحد على الأقل غير صالح.
type: docs
weight: 30
url: /ar/net/aspose.words.digitalsignatures/digitalsignaturecollection/isvalid/
---
## DigitalSignatureCollection.IsValid property

عوائد`حقيقي` إذا كانت جميع التوقيعات الرقمية في هذه المجموعة صالحة ولم يتم العبث بالمستند يتم إرجاعه أيضًا`حقيقي`في حالة عدم وجود توقيعات رقمية`خاطئة` إذا كان هناك توقيع رقمي واحد على الأقل غير صالح.

```csharp
public bool IsValid { get; }
```

### أمثلة

يوضح كيفية توقيع المستندات بشهادات X.509.

```csharp
// تحقق من عدم توقيع المستند.
Assert.False(FileFormatUtil.DetectFileFormat(MyDir + "Document.docx").HasDigitalSignature);

// أنشئ كائن CertificateHolder من ملف PKCS12 ، والذي سنستخدمه لتوقيع الوثيقة.
CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw", null);

// توجد طريقتان لحفظ نسخة موقعة من المستند في نظام الملفات المحلي:
// 1 - قم بتعيين مستند باسم ملف نظام محلي وحفظ نسخة موقعة في موقع محدد بواسطة اسم ملف آخر.
DigitalSignatureUtil.Sign(MyDir + "Document.docx", ArtifactsDir + "Document.DigitalSignature.docx", 
    certificateHolder, new SignOptions() { SignTime = DateTime.Now } );

Assert.True(FileFormatUtil.DetectFileFormat(ArtifactsDir + "Document.DigitalSignature.docx").HasDigitalSignature);

// 2 - خذ مستندًا من دفق واحفظ نسخة موقعة في دفق آخر.
using (FileStream inDoc = new FileStream(MyDir + "Document.docx", FileMode.Open))
{
    using (FileStream outDoc = new FileStream(ArtifactsDir + "Document.DigitalSignature.docx", FileMode.Create))
    {
        DigitalSignatureUtil.Sign(inDoc, outDoc, certificateHolder);
    }
}

Assert.True(FileFormatUtil.DetectFileFormat(ArtifactsDir + "Document.DigitalSignature.docx").HasDigitalSignature);

// الرجاء التحقق من أن جميع التوقيعات الرقمية الخاصة بالمستند صالحة وتحقق من تفاصيلها.
Document signedDoc = new Document(ArtifactsDir + "Document.DigitalSignature.docx");
DigitalSignatureCollection digitalSignatureCollection = signedDoc.DigitalSignatures;

Assert.True(digitalSignatureCollection.IsValid);
Assert.AreEqual(1, digitalSignatureCollection.Count);
Assert.AreEqual(DigitalSignatureType.XmlDsig, digitalSignatureCollection[0].SignatureType);
Assert.AreEqual("CN=Morzal.Me", signedDoc.DigitalSignatures[0].IssuerName);
Assert.AreEqual("CN=Morzal.Me", signedDoc.DigitalSignatures[0].SubjectName);
```

### أنظر أيضا

* class [DigitalSignatureCollection](../)
* مساحة الاسم [Aspose.Words.DigitalSignatures](../../digitalsignaturecollection/)
* المجسم [Aspose.Words](../../../)


