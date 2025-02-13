---
title: PdfEncryptionDetails.PdfEncryptionDetails
second_title: Aspose.Words لمراجع .NET API
description: PdfEncryptionDetails البناء. تهيئة مثيل لهذه الفئة .
type: docs
weight: 10
url: /ar/net/aspose.words.saving/pdfencryptiondetails/pdfencryptiondetails/
---
## PdfEncryptionDetails constructor

تهيئة مثيل لهذه الفئة .

```csharp
public PdfEncryptionDetails(string userPassword, string ownerPassword)
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

* class [PdfEncryptionDetails](../)
* مساحة الاسم [Aspose.Words.Saving](../../pdfencryptiondetails/)
* المجسم [Aspose.Words](../../../)


