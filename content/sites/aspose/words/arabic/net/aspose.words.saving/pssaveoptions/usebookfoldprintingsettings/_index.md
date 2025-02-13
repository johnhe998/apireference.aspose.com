---
title: PsSaveOptions.UseBookFoldPrintingSettings
second_title: Aspose.Words لمراجع .NET API
description: PsSaveOptions ملكية. الحصول على أو تعيين قيمة منطقية تشير إلى ما إذا كان يجب حفظ المستند باستخدام تخطيط طباعة كتيب  إذا تم تحديده عبرMultiplePages .
type: docs
weight: 30
url: /ar/net/aspose.words.saving/pssaveoptions/usebookfoldprintingsettings/
---
## PsSaveOptions.UseBookFoldPrintingSettings property

الحصول على أو تعيين قيمة منطقية تشير إلى ما إذا كان يجب حفظ المستند باستخدام تخطيط طباعة كتيب ، إذا تم تحديده عبر[`MultiplePages`](../../../aspose.words/pagesetup/multiplepages/) .

```csharp
public bool UseBookFoldPrintingSettings { get; set; }
```

### ملاحظات

إذا تم تحديد هذا الخيار ،[`PageSet`](../../fixedpagesaveoptions/pageset/) يتم تجاهلها عند الحفظ.

### أمثلة

يوضح كيفية حفظ مستند بتنسيق بوستسكريبت في شكل طية كتاب.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");

// قم بإنشاء كائن "PsSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة للوثيقة إلى PostScript.
// اضبط خاصية "UseBookFoldPrintingSettings" على "true" لترتيب المحتويات
// في مستند بوستسكريبت الناتج بطريقة تساعدنا في عمل كتيب منه.
// اضبط خاصية "UseBookFoldPrintingSettings" على "false" لحفظ المستند بشكل طبيعي.
PsSaveOptions saveOptions = new PsSaveOptions
{
    SaveFormat = SaveFormat.Ps,
    UseBookFoldPrintingSettings = renderTextAsBookFold
};

// إذا كنا نقدم المستند ككتيب ، فيجب علينا تعيين "صفحات متعددة"
// خصائص كائنات إعداد الصفحة لجميع الأقسام إلى "MultiplePagesType.BookFoldPrinting".
foreach (Section s in doc.Sections)
{
    s.PageSetup.MultiplePages = MultiplePagesType.BookFoldPrinting;
}

// بمجرد طباعة هذا المستند على كلا وجهي الصفحات ، يمكننا طي جميع الصفحات لأسفل في المنتصف مرة واحدة ،
// وستصطف المحتويات بطريقة تؤدي إلى إنشاء كتيب.
doc.Save(ArtifactsDir + "PsSaveOptions.UseBookFoldPrintingSettings.ps", saveOptions);
```

### أنظر أيضا

* class [PsSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../pssaveoptions/)
* المجسم [Aspose.Words](../../../)


