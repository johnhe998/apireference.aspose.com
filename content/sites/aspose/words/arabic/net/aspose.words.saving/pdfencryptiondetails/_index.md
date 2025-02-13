---
title: Class PdfEncryptionDetails
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Saving.PdfEncryptionDetails فصل. يحتوي على تفاصيل حول أذونات التشفير والوصول إلى مستند PDF .
type: docs
weight: 5180
url: /ar/net/aspose.words.saving/pdfencryptiondetails/
---
## PdfEncryptionDetails class

يحتوي على تفاصيل حول أذونات التشفير والوصول إلى مستند PDF .

```csharp
public class PdfEncryptionDetails
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [PdfEncryptionDetails](pdfencryptiondetails/)(string, string) | تهيئة مثيل لهذه الفئة . |

## الخصائص

| اسم | وصف |
| --- | --- |
| [OwnerPassword](../../aspose.words.saving/pdfencryptiondetails/ownerpassword/) { get; set; } | يحدد كلمة مرور المالك لمستند PDF المشفر. |
| [Permissions](../../aspose.words.saving/pdfencryptiondetails/permissions/) { get; set; } | يحدد العمليات المسموح بها للمستخدم في مستند PDF مشفر. القيمة الافتراضية هيDisallowAll . |
| [UserPassword](../../aspose.words.saving/pdfencryptiondetails/userpassword/) { get; set; } | يحدد كلمة مرور المستخدم المطلوبة لفتح مستند PDF المشفر. |

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

* مساحة الاسم [Aspose.Words.Saving](../../aspose.words.saving/)
* المجسم [Aspose.Words](../../)


