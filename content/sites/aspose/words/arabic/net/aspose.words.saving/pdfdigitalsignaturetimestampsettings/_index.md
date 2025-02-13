---
title: Class PdfDigitalSignatureTimestampSettings
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Saving.PdfDigitalSignatureTimestampSettings فصل. يحتوي على إعدادات الطابع الزمني للتوقيع الرقمي.
type: docs
weight: 5170
url: /ar/net/aspose.words.saving/pdfdigitalsignaturetimestampsettings/
---
## PdfDigitalSignatureTimestampSettings class

يحتوي على إعدادات الطابع الزمني للتوقيع الرقمي.

```csharp
public class PdfDigitalSignatureTimestampSettings
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [PdfDigitalSignatureTimestampSettings](pdfdigitalsignaturetimestampsettings/#constructor)() | تهيئة مثيل لهذه الفئة . |
| [PdfDigitalSignatureTimestampSettings](pdfdigitalsignaturetimestampsettings/#constructor_1)(string, string, string) | تهيئة مثيل لهذه الفئة . |
| [PdfDigitalSignatureTimestampSettings](pdfdigitalsignaturetimestampsettings/#constructor_2)(string, string, string, TimeSpan) | تهيئة مثيل لهذه الفئة . |

## الخصائص

| اسم | وصف |
| --- | --- |
| [Password](../../aspose.words.saving/pdfdigitalsignaturetimestampsettings/password/) { get; set; } | كلمة مرور خادم الطابع الزمني . |
| [ServerUrl](../../aspose.words.saving/pdfdigitalsignaturetimestampsettings/serverurl/) { get; set; } | عنوان URL لخادم الطابع الزمني . |
| [Timeout](../../aspose.words.saving/pdfdigitalsignaturetimestampsettings/timeout/) { get; set; } | قيمة المهلة للوصول إلى خادم الطابع الزمني. |
| [UserName](../../aspose.words.saving/pdfdigitalsignaturetimestampsettings/username/) { get; set; } | اسم مستخدم خادم الطابع الزمني. |

### أمثلة

يوضح كيفية توقيع مستند PDF محفوظ رقميًا وطابعه الزمني.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Signed PDF contents.");

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
PdfSaveOptions options = new PdfSaveOptions();

 // أنشئ توقيعًا رقميًا وقم بتعيينه إلى كائن SaveOptions الخاص بنا لتوقيع المستند عندما نحفظه في PDF.
CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
options.DigitalSignatureDetails = new PdfDigitalSignatureDetails(certificateHolder, "Test Signing", "Aspose Office", DateTime.Now);

// إنشاء طابع زمني تم التحقق منه من قِبل السلطة.
options.DigitalSignatureDetails.TimestampSettings =
    new PdfDigitalSignatureTimestampSettings("https://freetsa.org/tsr "،" JohnDoe "،" MyPassword ");

// العمر الافتراضي للطابع الزمني هو 100 ثانية.
Assert.AreEqual(100.0d, options.DigitalSignatureDetails.TimestampSettings.Timeout.TotalSeconds);

// يمكننا ضبط فترة المهلة عبر المُنشئ.
options.DigitalSignatureDetails.TimestampSettings =
    new PdfDigitalSignatureTimestampSettings("https://freetsa.org/tsr "،" JohnDoe "،" MyPassword "، TimeSpan.FromMinutes (30)) ;

Assert.AreEqual(1800.0d, options.DigitalSignatureDetails.TimestampSettings.Timeout.TotalSeconds);
Assert.AreEqual("https://freetsa.org/tsr "، options.DigitalSignatureDetails.TimestampSettings.ServerUrl) ;
Assert.AreEqual("JohnDoe", options.DigitalSignatureDetails.TimestampSettings.UserName);
Assert.AreEqual("MyPassword", options.DigitalSignatureDetails.TimestampSettings.Password);

// ستطبق طريقة "Save" توقيعنا على المستند الناتج في هذا الوقت.
doc.Save(ArtifactsDir + "PdfSaveOptions.PdfDigitalSignatureTimestamp.pdf", options);
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Saving](../../aspose.words.saving/)
* المجسم [Aspose.Words](../../)


