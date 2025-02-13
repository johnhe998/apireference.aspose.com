---
title: FixedPageSaveOptions.NumeralFormat
second_title: Aspose.Words لمراجع .NET API
description: FixedPageSaveOptions ملكية. يحصل أو يحددNumeralFormat تستخدم لعرض الأرقام. يتم استخدام الأرقام الأوروبية افتراضيًا.
type: docs
weight: 40
url: /ar/net/aspose.words.saving/fixedpagesaveoptions/numeralformat/
---
## FixedPageSaveOptions.NumeralFormat property

يحصل أو يحدد[`NumeralFormat`](../../numeralformat/) تستخدم لعرض الأرقام. يتم استخدام الأرقام الأوروبية افتراضيًا.

```csharp
public NumeralFormat NumeralFormat { get; set; }
```

### ملاحظات

إذا تم تغيير قيمة هذه الخاصية وتم إنشاء تخطيط الصفحة بالفعل ، فعندئذٍ [`UpdatePageLayout`](../../../aspose.words/document/updatepagelayout/) يتم استدعاؤه تلقائيًا لتحديث أي تغييرات.

### أمثلة

يوضح كيفية ضبط تنسيق الأرقام المستخدم عند الحفظ في PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = new CultureInfo("ar-AR").LCID;
builder.Writeln("1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 50, 100");

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
PdfSaveOptions options = new PdfSaveOptions();

// تعيين خاصية "NumeralFormat" إلى "NumeralFormat.ArabicIndic" إلى
// استخدم الحروف الرسومية من النطاق U + 0660 إلى U + 0669 كأرقام.
// قم بتعيين الخاصية "NumeralFormat" على "NumeralFormat.Context" إلى
// ابحث عن الإعدادات المحلية لتحديد عدد الحروف الرسومية المراد استخدامها.
// تعيين خاصية "NumeralFormat" إلى "NumeralFormat.EasternArabicIndic" إلى
// استخدم الحروف الرسومية من النطاق U + 06F0 إلى U + 06F9 كأرقام.
// اضبط خاصية "NumeralFormat" على "NumeralFormat.European" لاستخدام الأرقام الأوروبية.
// اضبط خاصية "NumeralFormat" على "NumeralFormat.System" لتحديد مجموعة الرموز من الإعدادات الإقليمية.
options.NumeralFormat = numeralFormat;

doc.Save(ArtifactsDir + "PdfSaveOptions.SetNumeralFormat.pdf", options);
```

### أنظر أيضا

* enum [NumeralFormat](../../numeralformat/)
* class [FixedPageSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../fixedpagesaveoptions/)
* المجسم [Aspose.Words](../../../)


