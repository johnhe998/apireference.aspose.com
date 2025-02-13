---
title: XpsSaveOptions.UseBookFoldPrintingSettings
second_title: Aspose.Words لمراجع .NET API
description: XpsSaveOptions ملكية. الحصول على أو تعيين قيمة منطقية تشير إلى ما إذا كان يجب حفظ المستند باستخدام تخطيط طباعة كتيب  إذا تم تحديده عبرMultiplePages .
type: docs
weight: 40
url: /ar/net/aspose.words.saving/xpssaveoptions/usebookfoldprintingsettings/
---
## XpsSaveOptions.UseBookFoldPrintingSettings property

الحصول على أو تعيين قيمة منطقية تشير إلى ما إذا كان يجب حفظ المستند باستخدام تخطيط طباعة كتيب ، إذا تم تحديده عبر[`MultiplePages`](../../../aspose.words/pagesetup/multiplepages/) .

```csharp
public bool UseBookFoldPrintingSettings { get; set; }
```

### ملاحظات

إذا تم تحديد هذا الخيار ،[`PageSet`](../../fixedpagesaveoptions/pageset/) يتم تجاهلها عند الحفظ.

### أمثلة

يوضح كيفية حفظ مستند بتنسيق XPS في شكل طية كتاب.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");

// قم بإنشاء كائن "XpsSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة للمستند إلى .XPS.
XpsSaveOptions xpsOptions = new XpsSaveOptions(SaveFormat.Xps);

// اضبط خاصية "UseBookFoldPrintingSettings" على "true" لترتيب المحتويات
// في إخراج XPS بطريقة تساعدنا في استخدامه لعمل كتيب.
// اضبط خاصية "UseBookFoldPrintingSettings" على "false" لعرض XPS بشكل طبيعي.
xpsOptions.UseBookFoldPrintingSettings = renderTextAsBookFold;

// إذا كنا نقدم المستند ككتيب ، فيجب علينا تعيين "صفحات متعددة"
// خصائص كائنات إعداد الصفحة لجميع الأقسام إلى "MultiplePagesType.BookFoldPrinting".
if (renderTextAsBookFold)
    foreach (Section s in doc.Sections)
    {
        s.PageSetup.MultiplePages = MultiplePagesType.BookFoldPrinting;
    }

// بمجرد طباعة هذا المستند ، يمكننا تحويله إلى كتيب عن طريق تكديس الصفحات
// ليخرج من الطابعة ويطوى من المنتصف.
doc.Save(ArtifactsDir + "XpsSaveOptions.BookFold.xps", xpsOptions);
```

### أنظر أيضا

* class [XpsSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../xpssaveoptions/)
* المجسم [Aspose.Words](../../../)


