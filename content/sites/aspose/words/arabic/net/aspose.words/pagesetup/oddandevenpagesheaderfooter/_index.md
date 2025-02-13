---
title: PageSetup.OddAndEvenPagesHeaderFooter
second_title: Aspose.Words لمراجع .NET API
description: PageSetup ملكية. حقيقيإذا كان المستند يحتوي على رؤوس وتذييلات مختلفة للصفحات المرقمة بأرقام فردية وزوجية.
type: docs
weight: 270
url: /ar/net/aspose.words/pagesetup/oddandevenpagesheaderfooter/
---
## PageSetup.OddAndEvenPagesHeaderFooter property

**حقيقي**إذا كان المستند يحتوي على رؤوس وتذييلات مختلفة للصفحات المرقمة بأرقام فردية وزوجية.

```csharp
public bool OddAndEvenPagesHeaderFooter { get; set; }
```

### ملاحظات

ملاحظة ، يؤثر تغيير هذه الخاصية على جميع أقسام المستند.

### أمثلة

يوضح كيفية إنشاء الرؤوس والتذييلات في مستند باستخدام DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// حدد أننا نريد رؤوس وتذييلات مختلفة للصفحات الأولى والزوجية والفردية.
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

// أنشئ الرؤوس ، ثم أضف ثلاث صفحات إلى المستند لعرض كل نوع رأس.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page3");

doc.Save(ArtifactsDir + "DocumentBuilder.HeadersAndFooters.docx");
```

يوضح كيفية تمكين أو تعطيل رؤوس / تذييلات الصفحات الزوجية.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// يوجد أدناه نوعان من الرؤوس / التذييلات.
// 1 - الرأس / التذييل "الأساسي" ، والذي يظهر في كل صفحة في القسم.
// يمكننا تجاوز الرأس / التذييل الأساسي برأس / تذييل الصفحة الأولى والزوجية.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Writeln("Primary header.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
builder.Writeln("Primary footer.");

// 2 - الرأس / التذييل "الزوجي" ، والذي يظهر في كل صفحة زوجية من هذا القسم.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Writeln("Even page header.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterEven);
builder.Writeln("Even page footer.");

builder.MoveToSection(0);
builder.Writeln("Page 1.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 2.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 3.");

// يحتوي كل قسم على كائن "PageSetup" يحدد الخصائص المتعلقة بمظهر الصفحة
// مثل الاتجاه والحجم والحدود.
// تعيين خاصية "OddAndEvenPagesHeaderFooter" على "true"
// لعرض رأس / تذييل الصفحة الزوجية على الصفحات الزوجية.
// تعيين خاصية "OddAndEvenPagesHeaderFooter" على "false"
// لعرض الرأس / التذييل الأساسي على الصفحات الزوجية.
builder.PageSetup.OddAndEvenPagesHeaderFooter = oddAndEvenPagesHeaderFooter;

doc.Save(ArtifactsDir + "PageSetup.OddAndEvenPagesHeaderFooter.docx");
```

### أنظر أيضا

* class [PageSetup](../)
* مساحة الاسم [Aspose.Words](../../pagesetup/)
* المجسم [Aspose.Words](../../../)


