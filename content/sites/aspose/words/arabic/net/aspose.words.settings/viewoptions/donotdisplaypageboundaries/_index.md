---
title: ViewOptions.DoNotDisplayPageBoundaries
second_title: Aspose.Words لمراجع .NET API
description: ViewOptions ملكية. إيقاف عرض المسافة بين أعلى النص والحافة العلوية للصفحة.
type: docs
weight: 20
url: /ar/net/aspose.words.settings/viewoptions/donotdisplaypageboundaries/
---
## ViewOptions.DoNotDisplayPageBoundaries property

إيقاف عرض المسافة بين أعلى النص والحافة العلوية للصفحة.

```csharp
public bool DoNotDisplayPageBoundaries { get; set; }
```

### أمثلة

يوضح كيفية إخفاء المسافات الرأسية والرؤوس / التذييلات في خيارات العرض.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل محتوى يمتد عبر 3 صفحات.
builder.Writeln("Paragraph 1, Page 1.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Paragraph 2, Page 2.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Paragraph 3, Page 3.");

// أدخل رأس وتذييل.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Writeln("This is the header.");
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
builder.Writeln("This is the footer.");

// يحتوي هذا المستند على قدر صغير من المحتوى يشغل مساحة قليلة من الصفحات الكاملة.
// قم بتعيين علامة "DoNotDisplayPageBoundaries" على "true" للحصول على إصدارات أقدم من Microsoft Word لحذف الرؤوس ،
// التذييلات ، والكثير من المسافات الرأسية عند عرض المستند.
// قم بتعيين علامة "DoNotDisplayPageBoundaries" على "خطأ" للحصول على إصدارات أقدم من Microsoft Word
// لعرض وثيقتنا بشكل طبيعي.
doc.ViewOptions.DoNotDisplayPageBoundaries = doNotDisplayPageBoundaries;

doc.Save(ArtifactsDir + "ViewOptions.DisplayPageBoundaries.doc");
```

### أنظر أيضا

* class [ViewOptions](../)
* مساحة الاسم [Aspose.Words.Settings](../../viewoptions/)
* المجسم [Aspose.Words](../../../)


