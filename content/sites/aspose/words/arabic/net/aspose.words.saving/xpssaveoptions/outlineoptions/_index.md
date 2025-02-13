---
title: XpsSaveOptions.OutlineOptions
second_title: Aspose.Words لمراجع .NET API
description: XpsSaveOptions ملكية. يسمح بتحديد خيارات المخطط التفصيلي .
type: docs
weight: 20
url: /ar/net/aspose.words.saving/xpssaveoptions/outlineoptions/
---
## XpsSaveOptions.OutlineOptions property

يسمح بتحديد خيارات المخطط التفصيلي .

```csharp
public OutlineOptions OutlineOptions { get; }
```

### ملاحظات

لاحظ أن خيار ExpandedOutlineLevels لن يعمل عند الحفظ في XPS.

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

* class [OutlineOptions](../../outlineoptions/)
* class [XpsSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../xpssaveoptions/)
* المجسم [Aspose.Words](../../../)


