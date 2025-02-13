---
title: PdfSaveOptions.EncryptionDetails
second_title: Aspose.Words لمراجع .NET API
description: PdfSaveOptions ملكية. الحصول على أو تعيين التفاصيل الخاصة بتشفير مستند PDF الناتج.
type: docs
weight: 110
url: /ar/net/aspose.words.saving/pdfsaveoptions/encryptiondetails/
---
## PdfSaveOptions.EncryptionDetails property

الحصول على أو تعيين التفاصيل الخاصة بتشفير مستند PDF الناتج.

```csharp
public PdfEncryptionDetails EncryptionDetails { get; set; }
```

### ملاحظات

القيمة الافتراضية خالية ولن يتم تشفير مستند الإخراج . عند تعيين هذه الخاصية على قيمة صالحة[`PdfEncryptionDetails`](../../pdfencryptiondetails/) الكائن ، ثم سيتم تشفير مستند PDF الناتج.

يتم استخدام خوارزمية تشفير AES-128 عند الحفظ إلى التوافق المستند إلى PDF 1.7 (بما في ذلك PDF / UA-1) . يتم استخدام خوارزمية تشفير AES-256 عند الحفظ إلى التوافق المستند إلى PDF 2.0.

يحظر التشفير من خلال التوافق مع PDF / A. سيتم تجاهل هذا الخيار عند الحفظ في PDF / A.

ContentCopyForAccessibilityمطلوب إذن من قبل التوافق مع PDF / UA إذا كان المستند الناتج مشفرًا. سيتم استخدام هذا الإذن تلقائيًا عند الحفظ في PDF / UA.

ContentCopyForAccessibility تم إهمال الإذن بتنسيق PDF 2.0. سيتم تجاهل هذا الإذن عند الحفظ في PDF 2.0.

### أمثلة

يوضح كيفية تعيين الأذونات على مستند PDF محفوظ.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");

PdfEncryptionDetails encryptionDetails =
    new PdfEncryptionDetails("password", string.Empty);

// ابدأ برفض جميع الأذونات.
encryptionDetails.Permissions = PdfPermissions.DisallowAll;

// تمديد الأذونات للسماح بتحرير التعليقات التوضيحية.
encryptionDetails.Permissions = PdfPermissions.ModifyAnnotations | PdfPermissions.DocumentAssembly;

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// تمكين التشفير عبر خاصية "EncryptionDetails".
saveOptions.EncryptionDetails = encryptionDetails;

// عندما نفتح هذا المستند ، سنحتاج إلى توفير كلمة المرور قبل الوصول إلى محتوياته.
doc.Save(ArtifactsDir + "PdfSaveOptions.EncryptionPermissions.pdf", saveOptions);
```

### أنظر أيضا

* class [PdfEncryptionDetails](../../pdfencryptiondetails/)
* class [PdfSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../pdfsaveoptions/)
* المجسم [Aspose.Words](../../../)


