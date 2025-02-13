---
title: Paragraph.BreakIsStyleSeparator
second_title: Aspose.Words لمراجع .NET API
description: Paragraph ملكية. صواب إذا كان فاصل الفقرة هذا عبارة عن فاصل نمط. يسمح فاصل الأنماط بفقرة واحدة لتتكون من أجزاء لها أنماط فقرة مختلفة.
type: docs
weight: 20
url: /ar/net/aspose.words/paragraph/breakisstyleseparator/
---
## Paragraph.BreakIsStyleSeparator property

صواب إذا كان فاصل الفقرة هذا عبارة عن فاصل نمط. يسمح فاصل الأنماط بفقرة واحدة لتتكون من أجزاء لها أنماط فقرة مختلفة.

```csharp
public bool BreakIsStyleSeparator { get; }
```

### أمثلة

يوضح كيفية كتابة نص على نفس السطر كعنوان جدول المحتويات وعدم ظهوره في جدول المحتويات.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertTableOfContents("\\o \\h \\z \\u");
builder.InsertBreak(BreakType.PageBreak);

// أدخل فقرة بنمط يختاره جدول المحتويات كإدخال.
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

// كلا هاتين الجملتين في نفس الفقرة وبالتالي ستظهران في نفس إدخال جدول المحتويات.
builder.Write("Heading 1. ");
builder.Write("Will appear in the TOC. ");

// إذا أدخلنا فاصل نمط ، فيمكننا كتابة المزيد من النص في نفس الفقرة
// واستخدم أسلوبًا مختلفًا دون الظهور في جدول المحتويات.
// إذا استخدمنا نمط نوع العنوان بعد الفاصل ، فيمكننا رسم إدخالات جدول المحتويات المتعددة من سطر نص مستند واحد.
builder.InsertStyleSeparator();
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Quote;
builder.Write("Won't appear in the TOC. ");

Assert.True(doc.FirstSection.Body.FirstParagraph.BreakIsStyleSeparator);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Paragraph.BreakIsStyleSeparator.docx");
```

### أنظر أيضا

* class [Paragraph](../)
* مساحة الاسم [Aspose.Words](../../paragraph/)
* المجسم [Aspose.Words](../../../)


