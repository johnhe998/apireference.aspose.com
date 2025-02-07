---
title: Class LayoutOptions
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Layout.LayoutOptions فصل. يحتوي على الخيارات التي تسمح بالتحكم في عملية تخطيط المستند.
type: docs
weight: 3150
url: /ar/net/aspose.words.layout/layoutoptions/
---
## LayoutOptions class

يحتوي على الخيارات التي تسمح بالتحكم في عملية تخطيط المستند.

```csharp
public class LayoutOptions
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [LayoutOptions](layoutoptions/)() | Default_Constructor |

## الخصائص

| اسم | وصف |
| --- | --- |
| [Callback](../../aspose.words.layout/layoutoptions/callback/) { get; set; } | يحصل أو يحدد[`IPageLayoutCallback`](../ipagelayoutcallback/)التنفيذ المستخدم بواسطة نموذج تخطيط الصفحة. |
| [CommentDisplayMode](../../aspose.words.layout/layoutoptions/commentdisplaymode/) { get; set; } | الحصول على أو تحديد طريقة عرض التعليقات. القيمة الافتراضية هيShowInBalloons . |
| [ContinuousSectionPageNumberingRestart](../../aspose.words.layout/layoutoptions/continuoussectionpagenumberingrestart/) { get; set; } | الحصول على أو تعيين وضع السلوك لحساب أرقام الصفحات عندما يقوم قسم مستمر بإعادة تشغيل ترقيم الصفحات . |
| [IgnorePrinterMetrics](../../aspose.words.layout/layoutoptions/ignoreprintermetrics/) { get; set; } | الحصول على أو تعيين إشارة إلى ما إذا كان يتم تجاهل خيار التوافق "استخدام مقاييس الطابعة لتخطيط المستند". القيمة الافتراضية هي True . |
| [RevisionOptions](../../aspose.words.layout/layoutoptions/revisionoptions/) { get; } | يحصل على خيارات المراجعة . |
| [ShowHiddenText](../../aspose.words.layout/layoutoptions/showhiddentext/) { get; set; } | الحصول على أو تعيين إشارة إلى ما إذا كان النص المخفي في المستند سيتم تقديمه أم لا. الإعداد الافتراضي خطأ. |
| [ShowParagraphMarks](../../aspose.words.layout/layoutoptions/showparagraphmarks/) { get; set; } | الحصول على أو تعيين إشارة إلى ما إذا كان يتم تقديم علامات الفقرات. الإعداد الافتراضي هو False . |
| [TextShaperFactory](../../aspose.words.layout/layoutoptions/textshaperfactory/) { get; set; } | يحصل أو يحدد[`ITextShaperFactory`](../../aspose.words.shaping/itextshaperfactory/) التنفيذ المستخدم لميزات عرض الطباعة المتقدمة. |

### ملاحظات

لا يمكنك إنشاء مثيلات من هذه الفئة مباشرة. استخدم ال[`LayoutOptions`](../../aspose.words/document/layoutoptions/)الخاصية للوصول إلى خيارات التخطيط لهذا المستند.

لاحظ أنه بعد تغيير أي من الخيارات الموجودة في هذا الفصل ،[`UpdatePageLayout`](../../aspose.words/document/updatepagelayout/) يجب استدعاء method من أجل تطبيق الخيارات المتغيرة على التخطيط.

### أمثلة

يوضح كيفية إخفاء النص في مستند الإخراج المعروض.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
// أدخل نصًا مخفيًا ، ثم حدد ما إذا كنا نرغب في حذفه من المستند المقدم.
builder.Writeln("This text is not hidden.");
builder.Font.Hidden = true;
builder.Writeln("This text is hidden.");

doc.LayoutOptions.ShowHiddenText = showHiddenText;

doc.Save(ArtifactsDir + "Document.LayoutOptionsHiddenText.pdf");
```

يوضح كيفية إظهار علامات الفقرات في مستند الإخراج الذي تم تقديمه.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
// أضف بعض الفقرات ، ثم قم بتمكين علامات الفقرات لإظهار نهايات الفقرات
// مع رمز بيلكرو (¶) عند تقديم المستند.
builder.Writeln("Hello world!");
builder.Writeln("Hello again!");

doc.LayoutOptions.ShowParagraphMarks = showParagraphMarks;

doc.Save(ArtifactsDir + "Document.LayoutOptionsParagraphMarks.pdf");
```

يوضح كيفية تغيير مظهر المراجعات في مستند الإخراج الذي تم تقديمه.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل مراجعة ، ثم قم بتغيير لون جميع المراجعات إلى اللون الأخضر.
builder.Writeln("This is not a revision.");
doc.StartTrackRevisions("John Doe", DateTime.Now);
builder.Writeln("This is a revision.");
doc.StopTrackRevisions();
builder.Writeln("This is not a revision.");

// قم بإزالة الشريط الذي يظهر على يسار كل سطر تمت مراجعته.
doc.LayoutOptions.RevisionOptions.InsertedTextColor = RevisionColor.BrightGreen;
doc.LayoutOptions.RevisionOptions.ShowRevisionBars = false;

doc.Save(ArtifactsDir + "Document.LayoutOptionsRevisions.pdf");
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Layout](../../aspose.words.layout/)
* المجسم [Aspose.Words](../../)


