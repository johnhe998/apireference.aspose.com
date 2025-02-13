---
title: PdfSaveOptions.Compliance
second_title: Aspose.Words لمراجع .NET API
description: PdfSaveOptions ملكية. يحدد مستوى التوافق مع معايير PDF لمستندات الإخراج.
type: docs
weight: 30
url: /ar/net/aspose.words.saving/pdfsaveoptions/compliance/
---
## PdfSaveOptions.Compliance property

يحدد مستوى التوافق مع معايير PDF لمستندات الإخراج.

```csharp
public PdfCompliance Compliance { get; set; }
```

### ملاحظات

الافتراضي هوPdf17.

### أمثلة

يوضح كيفية تعيين مستوى التوافق مع معايير PDF لمستندات PDF المحفوظة.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
// لاحظ أن بعض خيارات PdfSaveOptions محظورة عند الحفظ في أحد المعايير ويتم إصلاحها تلقائيًا.
// استخدم IWarningCallback لمعرفة الخيارات التي يتم إصلاحها تلقائيًا.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// اضبط خاصية "Compliance" على "PdfCompliance.PdfA1b" للامتثال لمعيار "PDF / A-1b" ،
// الذي يهدف إلى الحفاظ على المظهر المرئي للوثيقة مثل Aspose ، وتحول الكلمات إلى PDF.
// عيِّن خاصية "الامتثال" على "PdfCompliance.Pdf17" لتتوافق مع المعيار "1.7".
// قم بتعيين خاصية "الامتثال" على "PdfCompliance.PdfA1a" للامتثال لمعيار "PDF / A-1a" ،
// الذي يتوافق مع "PDF / A-1b" بالإضافة إلى الحفاظ على بنية المستند الأصلي.
// قم بتعيين خاصية "الامتثال" على "PdfCompliance.PdfUa1" للامتثال لمعيار "PDF / UA-1" (ISO 14289-1) ،
// الذي يهدف إلى تحديد تمثيل المستندات الإلكترونية في PDF والتي تسمح بالوصول إلى الملف.
// يساعد هذا في جعل المستندات قابلة للبحث ولكن قد يزيد بشكل كبير من حجم المستندات الكبيرة بالفعل.
saveOptions.Compliance = pdfCompliance;

doc.Save(ArtifactsDir + "PdfSaveOptions.Compliance.pdf", saveOptions);
```

### أنظر أيضا

* enum [PdfCompliance](../../pdfcompliance/)
* class [PdfSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../pdfsaveoptions/)
* المجسم [Aspose.Words](../../../)


