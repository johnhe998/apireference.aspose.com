---
title: TxtSaveOptionsBase.ForcePageBreaks
second_title: Aspose.Words لمراجع .NET API
description: TxtSaveOptionsBase ملكية. يسمح بتحديد ما إذا كان يجب الاحتفاظ بفواصل الصفحات أثناء التصدير.
type: docs
weight: 30
url: /ar/net/aspose.words.saving/txtsaveoptionsbase/forcepagebreaks/
---
## TxtSaveOptionsBase.ForcePageBreaks property

يسمح بتحديد ما إذا كان يجب الاحتفاظ بفواصل الصفحات أثناء التصدير.

النظام الأساسي **خاطئة**.

```csharp
public bool ForcePageBreaks { get; set; }
```

### ملاحظات

تؤثر الخاصية فقط على فواصل الصفحات التي يتم إدراجها بشكل صريح في المستند. لا يتعلق الأمر بفواصل الصفحات التي يقوم MS Word بإدراجها تلقائيًا في نهاية كل صفحة.

### أمثلة

يوضح كيفية تحديد ما إذا كان سيتم الاحتفاظ بفواصل الصفحات عند تصدير مستند إلى نص عادي.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Page 1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 2");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 3");

// قم بإنشاء كائن "TxtSaveOptions" ، والذي يمكننا تمريره إلى "حفظ" المستند
// لتعديل كيفية حفظ المستند إلى نص عادي.
TxtSaveOptions saveOptions = new TxtSaveOptions();

// تحتوي كائنات "مستند" Aspose.Words على فواصل صفحات ، تمامًا مثل مستندات Microsoft Word.
// حفظ التنسيقات مثل ".txt" هي نص واحد متواصل من النص بدون فواصل صفحات.
// اضبط خاصية "ForcePageBreaks" على "true" للحفاظ على جميع فواصل الصفحات في شكل أحرف '\ f'.
// اضبط خاصية "ForcePageBreaks" على "خطأ" لتجاهل كافة فواصل الصفحات.
saveOptions.ForcePageBreaks = forcePageBreaks;

doc.Save(ArtifactsDir + "TxtSaveOptions.PageBreaks.txt", saveOptions);

// إذا قمنا بتحميل مستند نص عادي مع فواصل الصفحات ،
// سيستخدمها كائن "المستند" لتقسيم النص إلى صفحات.
doc = new Document(ArtifactsDir + "TxtSaveOptions.PageBreaks.txt");

Assert.AreEqual(forcePageBreaks ? 3 : 1, doc.PageCount);
```

### أنظر أيضا

* class [TxtSaveOptionsBase](../)
* مساحة الاسم [Aspose.Words.Saving](../../txtsaveoptionsbase/)
* المجسم [Aspose.Words](../../../)


