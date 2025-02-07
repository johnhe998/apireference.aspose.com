---
title: Class OutlineOptions
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Saving.OutlineOptions فصل. يسمح بتحديد خيارات المخطط التفصيلي .
type: docs
weight: 5080
url: /ar/net/aspose.words.saving/outlineoptions/
---
## OutlineOptions class

يسمح بتحديد خيارات المخطط التفصيلي .

```csharp
public class OutlineOptions
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [OutlineOptions](outlineoptions/)() | Default_Constructor |

## الخصائص

| اسم | وصف |
| --- | --- |
| [BookmarksOutlineLevels](../../aspose.words.saving/outlineoptions/bookmarksoutlinelevels/) { get; } | يسمح بتحديد مستوى مخطط الإشارات المرجعية الفردية. |
| [CreateMissingOutlineLevels](../../aspose.words.saving/outlineoptions/createmissingoutlinelevels/) { get; set; } | الحصول على أو تعيين قيمة تحدد ما إذا كان سيتم إنشاء مستويات مخطط تفصيلي مفقودة أم لا عندما يتم تصدير المستند . |
| [CreateOutlinesForHeadingsInTables](../../aspose.words.saving/outlineoptions/createoutlinesforheadingsintables/) { get; set; } | يحدد ما إذا كان سيتم إنشاء مخططات تفصيلية للعناوين (فقرات منسقة باستخدام أنماط العناوين) داخل الجداول. |
| [DefaultBookmarksOutlineLevel](../../aspose.words.saving/outlineoptions/defaultbookmarksoutlinelevel/) { get; set; } | يحدد المستوى الافتراضي في مخطط المستند الذي يتم عنده عرض إشارات مرجعية لـ Word. |
| [ExpandedOutlineLevels](../../aspose.words.saving/outlineoptions/expandedoutlinelevels/) { get; set; } | يحدد عدد المستويات في مخطط المستند لإظهاره موسعًا عند عرض الملف. |
| [HeadingsOutlineLevels](../../aspose.words.saving/outlineoptions/headingsoutlinelevels/) { get; set; } | يحدد عدد مستويات العناوين (الفقرات المنسقة بأنماط العناوين) التي سيتم تضمينها في مخطط المستند . |

### أمثلة

يظهر لمعالجة الإشارات المرجعية في الرؤوس / التذييلات في مستند نقوم بتقديمه إلى PDF.

```csharp
Document doc = new Document(MyDir + "Bookmarks in headers and footers.docx");

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// اضبط خاصية "PageMode" على "PdfPageMode.UseOutlines" لعرض جزء التنقل في المخطط التفصيلي في ملف PDF الناتج.
saveOptions.PageMode = PdfPageMode.UseOutlines;

// اضبط خاصية "DefaultBookmarksOutlineLevel" على "1" لعرض الكل
// الإشارات المرجعية في المستوى الأول من المخطط التفصيلي في ملف PDF الناتج.
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;

// تعيين خاصية "HeaderFooterBookmarksExportMode" على "HeaderFooterBookmarksExportMode.None" إلى
// لا تصدر أي إشارات مرجعية موجودة داخل الرؤوس / التذييلات.
// تعيين خاصية "HeaderFooterBookmarksExportMode" على "HeaderFooterBookmarksExportMode.First" إلى
// فقط تصدير الإشارات المرجعية في رأس / تذييلات القسم الأول.
// تعيين خاصية "HeaderFooterBookmarksExportMode" على "HeaderFooterBookmarksExportMode.All" إلى
// تصدير الإشارات المرجعية الموجودة في جميع الرؤوس / التذييلات.
saveOptions.HeaderFooterBookmarksExportMode = headerFooterBookmarksExportMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.HeaderFooterBookmarksExportMode.pdf", saveOptions);
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Saving](../../aspose.words.saving/)
* المجسم [Aspose.Words](../../)


