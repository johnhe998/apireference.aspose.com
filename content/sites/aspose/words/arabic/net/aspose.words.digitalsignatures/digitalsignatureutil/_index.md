---
title: Class DigitalSignatureUtil
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.DigitalSignatures.DigitalSignatureUtil فصل. يوفر طرقًا لتوقيع المستند.
type: docs
weight: 400
url: /ar/net/aspose.words.digitalsignatures/digitalsignatureutil/
---
## DigitalSignatureUtil class

يوفر طرقًا لتوقيع المستند.

```csharp
public static class DigitalSignatureUtil
```

## طُرق

| اسم | وصف |
| --- | --- |
| static [LoadSignatures](../../aspose.words.digitalsignatures/digitalsignatureutil/loadsignatures/#loadsignatures)(Stream) | تحميل التوقيعات الرقمية من المستند باستخدام الدفق. |
| static [LoadSignatures](../../aspose.words.digitalsignatures/digitalsignatureutil/loadsignatures/#loadsignatures_1)(string) | تحميل التوقيعات الرقمية من المستند. |
| static [RemoveAllSignatures](../../aspose.words.digitalsignatures/digitalsignatureutil/removeallsignatures/#removeallsignatures)(Stream, Stream) | يزيل جميع التوقيعات الرقمية من المستند في دفق المصدر ويكتب المستند غير الموقعة إلى تيار الوجهة. |
| static [RemoveAllSignatures](../../aspose.words.digitalsignatures/digitalsignatureutil/removeallsignatures/#removeallsignatures_1)(string, string) | يزيل كافة التوقيعات الرقمية من الملف المصدر ويكتب ملفًا غير موقع إلى ملف الوجهة. |
| static [Sign](../../aspose.words.digitalsignatures/digitalsignatureutil/sign/#sign)(Stream, Stream, CertificateHolder) | يوقع المستند المصدر باستخدام معين[`CertificateHolder`](../certificateholder/)مع التوقيع الرقمي_ ويكتب المستند الموقع إلى تيار الوجهة. |
| static [Sign](../../aspose.words.digitalsignatures/digitalsignatureutil/sign/#sign_2)(string, string, CertificateHolder) | يوقع المستند المصدر باستخدام معين[`CertificateHolder`](../certificateholder/) مع التوقيع الرقمي_ وكتابة المستند الموقع إلى الملف الوجهة. |
| static [Sign](../../aspose.words.digitalsignatures/digitalsignatureutil/sign/#sign_1)(Stream, Stream, CertificateHolder, SignOptions) | يوقع المستند المصدر باستخدام معين[`CertificateHolder`](../certificateholder/) و[`SignOptions`](../signoptions/) بالتوقيع الرقمي ويكتب المستند الموقع إلى تيار الوجهة. |
| static [Sign](../../aspose.words.digitalsignatures/digitalsignatureutil/sign/#sign_3)(string, string, CertificateHolder, SignOptions) | يوقع المستند المصدر باستخدام معين[`CertificateHolder`](../certificateholder/) و[`SignOptions`](../signoptions/) بالتوقيع الرقمي ويكتب المستند الموقع إلى ملف الوجهة. |

### ملاحظات

نظرًا لأن التوقيع الرقمي يعمل مع محتوى الملف بدلاً من نموذج كائن المستند ، يتم وضع هذه الطرق في فئة منفصلة.

التنسيقات المدعومة هيDoc وDocx.

### أمثلة

يوضح كيفية تحميل التوقيعات من مستند موقع رقميًا.

```csharp
// هناك طريقتان لتحميل مجموعة التوقيعات الرقمية الخاصة بوثيقة موقعة باستخدام فئة DigitalSignatureUtil.
// 1 - تحميل من مستند من اسم ملف نظام ملفات محلي:
DigitalSignatureCollection digitalSignatures = 
    DigitalSignatureUtil.LoadSignatures(MyDir + "Digitally signed.docx");

// إذا كانت هذه المجموعة غير فارغة ، فيمكننا التحقق من توقيع المستند رقميًا.
Assert.AreEqual(1, digitalSignatures.Count);

// 2 - تحميل من مستند من FileStream:
using (Stream stream = new FileStream(MyDir + "Digitally signed.docx", FileMode.Open))
{
    digitalSignatures = DigitalSignatureUtil.LoadSignatures(stream);
    Assert.AreEqual(1, digitalSignatures.Count);
}
```

يوضح كيفية إزالة التواقيع الرقمية من مستند موقع رقميًا.

```csharp
// هناك طريقتان لاستخدام فئة DigitalSignatureUtil لإزالة التوقيعات الرقمية
// من مستند موقع عن طريق حفظ نسخة غير موقعة منه في مكان آخر في نظام الملفات المحلي.
// 1 - تحديد مواقع كل من المستند الموقع والنسخة غير الموقعة بواسطة سلاسل اسم الملف:
DigitalSignatureUtil.RemoveAllSignatures(MyDir + "Digitally signed.docx",
    ArtifactsDir + "DigitalSignatureUtil.LoadAndRemove.FromString.docx");

// 2 - تحديد مواقع كل من المستند الموقع والنسخة غير الموقعة بواسطة تدفقات الملفات:
using (Stream streamIn = new FileStream(MyDir + "Digitally signed.docx", FileMode.Open))
{
    using (Stream streamOut = new FileStream(ArtifactsDir + "DigitalSignatureUtil.LoadAndRemove.FromStream.docx", FileMode.Create))
    {
        DigitalSignatureUtil.RemoveAllSignatures(streamIn, streamOut);
    }
}

// تحقق من أن كلا من وثيقتنا المخرجة لا تحتوي على توقيعات رقمية.
Assert.That(DigitalSignatureUtil.LoadSignatures(ArtifactsDir + "DigitalSignatureUtil.LoadAndRemove.FromString.docx"), Is.Empty);
Assert.That(DigitalSignatureUtil.LoadSignatures(ArtifactsDir + "DigitalSignatureUtil.LoadAndRemove.FromStream.docx"), Is.Empty);
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.DigitalSignatures](../../aspose.words.digitalsignatures/)
* المجسم [Aspose.Words](../../)


