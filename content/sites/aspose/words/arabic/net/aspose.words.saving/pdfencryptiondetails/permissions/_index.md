---
title: PdfEncryptionDetails.Permissions
second_title: Aspose.Words لمراجع .NET API
description: PdfEncryptionDetails ملكية. يحدد العمليات المسموح بها للمستخدم في مستند PDF مشفر. القيمة الافتراضية هيDisallowAll .
type: docs
weight: 30
url: /ar/net/aspose.words.saving/pdfencryptiondetails/permissions/
---
## PdfEncryptionDetails.Permissions property

يحدد العمليات المسموح بها للمستخدم في مستند PDF مشفر. القيمة الافتراضية هيDisallowAll .

```csharp
public PdfPermissions Permissions { get; set; }
```

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

* enum [PdfPermissions](../../pdfpermissions/)
* class [PdfEncryptionDetails](../)
* مساحة الاسم [Aspose.Words.Saving](../../pdfencryptiondetails/)
* المجسم [Aspose.Words](../../../)


