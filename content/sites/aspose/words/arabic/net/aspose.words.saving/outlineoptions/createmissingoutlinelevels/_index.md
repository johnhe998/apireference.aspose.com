---
title: OutlineOptions.CreateMissingOutlineLevels
second_title: Aspose.Words لمراجع .NET API
description: OutlineOptions ملكية. الحصول على أو تعيين قيمة تحدد ما إذا كان سيتم إنشاء مستويات مخطط تفصيلي مفقودة أم لا عندما يتم تصدير المستند .
type: docs
weight: 30
url: /ar/net/aspose.words.saving/outlineoptions/createmissingoutlinelevels/
---
## OutlineOptions.CreateMissingOutlineLevels property

الحصول على أو تعيين قيمة تحدد ما إذا كان سيتم إنشاء مستويات مخطط تفصيلي مفقودة أم لا عندما يتم تصدير المستند .

القيمة الافتراضية لهذه الخاصية هي **خاطئة**.

```csharp
public bool CreateMissingOutlineLevels { get; set; }
```

### أمثلة

يوضح كيفية العمل بمستويات المخطط التفصيلي التي لا تحتوي على أي عناوين مقابلة عند حفظ مستند PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل العناوين التي يمكن أن تكون بمثابة مدخلات جدول المحتويات للمستويين 1 و 5.
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

Assert.True(builder.ParagraphFormat.IsHeading);

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading5;

builder.Writeln("Heading 1.1.1.1.1");
builder.Writeln("Heading 1.1.1.1.2");

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// سيحتوي مستند PDF الناتج على مخطط تفصيلي ، وهو جدول محتويات يسرد العناوين في نص المستند.
// سيأخذنا النقر فوق إدخال في هذا المخطط التفصيلي إلى موقع العنوان الخاص به.
// قم بتعيين خاصية "HeadingsOutlineLevels" على "5" لتضمين كافة عناوين المستويات 5 وما دونها في المخطط التفصيلي.
saveOptions.OutlineOptions.HeadingsOutlineLevels = 5;

 // يحتوي هذا المستند على عناوين المستويات 1 و 5 ، ولا توجد عناوين بالمستويات 2 و 3 و 4.
// سيعامل مستند PDF الناتج مستويات المخطط التفصيلي 2 و 3 و 4 على أنها "مفقودة".
// قم بتعيين خاصية "CreateMissingOutlineLevels" على "true" لتضمين جميع المستويات المفقودة في المخطط التفصيلي ،
// ترك إدخالات فارغة في المخطط التفصيلي نظرًا لعدم وجود عناوين قابلة للاستخدام.
// اضبط خاصية "CreateMissingOutlineLevels" على "false" لتجاهل مستويات المخطط التفصيلي المفقودة ،
// والتعامل مع عناوين المخطط التفصيلي من المستوى 5 كمستوى 2.
saveOptions.OutlineOptions.CreateMissingOutlineLevels = createMissingOutlineLevels;

doc.Save(ArtifactsDir + "PdfSaveOptions.CreateMissingOutlineLevels.pdf", saveOptions);
```

### أنظر أيضا

* class [OutlineOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../outlineoptions/)
* المجسم [Aspose.Words](../../../)


