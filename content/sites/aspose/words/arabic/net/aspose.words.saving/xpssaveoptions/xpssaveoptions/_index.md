---
title: XpsSaveOptions.XpsSaveOptions
second_title: Aspose.Words لمراجع .NET API
description: XpsSaveOptions البناء. تهيئة مثيل جديد من هذه الفئة يمكن استخدامه لحفظ document فيXps التنسيق .
type: docs
weight: 10
url: /ar/net/aspose.words.saving/xpssaveoptions/xpssaveoptions/
---
## XpsSaveOptions() {#constructor}

تهيئة مثيل جديد من هذه الفئة يمكن استخدامه لحفظ document فيXps التنسيق .

```csharp
public XpsSaveOptions()
```

### أمثلة

يوضح كيفية تحديد مستوى العناوين التي ستظهر في مخطط مستند XPS محفوظ.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل العناوين التي يمكن أن تكون بمثابة مدخلات جدول المحتويات للمستويات 1 و 2 ثم 3.
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

Assert.True(builder.ParagraphFormat.IsHeading);

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 1.2.1");
builder.Writeln("Heading 1.2.2");

// قم بإنشاء كائن "XpsSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة للمستند إلى .XPS.
XpsSaveOptions saveOptions = new XpsSaveOptions();

Assert.AreEqual(SaveFormat.Xps, saveOptions.SaveFormat);

// سيحتوي مستند XPS الناتج على مخطط تفصيلي وجدول محتويات يسرد العناوين في نص المستند.
// سيأخذنا النقر فوق إدخال في هذا المخطط التفصيلي إلى موقع العنوان الخاص به.
// قم بتعيين خاصية "HeadingsOutlineLevels" على "2" لاستبعاد كافة العناوين التي تكون مستوياتها أعلى من 2 من المخطط التفصيلي.
// لن يظهر العنوانان الأخيران اللذان أدخلاهما أعلاه.
saveOptions.OutlineOptions.HeadingsOutlineLevels = 2;

doc.Save(ArtifactsDir + "XpsSaveOptions.OutlineLevels.xps", saveOptions);
```

### أنظر أيضا

* class [XpsSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../xpssaveoptions/)
* المجسم [Aspose.Words](../../../)

---

## XpsSaveOptions(SaveFormat) {#constructor_1}

تهيئة مثيل جديد من هذه الفئة يمكن استخدامه لحفظ document فيXps أوOpenXps التنسيق .

```csharp
public XpsSaveOptions(SaveFormat saveFormat)
```

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

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [XpsSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../xpssaveoptions/)
* المجسم [Aspose.Words](../../../)


