---
title: PdfSaveOptions.HeaderFooterBookmarksExportMode
second_title: Aspose.Words لمراجع .NET API
description: PdfSaveOptions ملكية. يحدد كيفية تصدير الإشارات المرجعية في الرؤوس / التذييلات .
type: docs
weight: 150
url: /ar/net/aspose.words.saving/pdfsaveoptions/headerfooterbookmarksexportmode/
---
## PdfSaveOptions.HeaderFooterBookmarksExportMode property

يحدد كيفية تصدير الإشارات المرجعية في الرؤوس / التذييلات .

```csharp
public HeaderFooterBookmarksExportMode HeaderFooterBookmarksExportMode { get; set; }
```

### ملاحظات

النظام الأساسيAll.

يتم استخدام هذه الخاصية بالاشتراك مع[`OutlineOptions`](../outlineoptions/) اختيار.

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

* enum [HeaderFooterBookmarksExportMode](../../headerfooterbookmarksexportmode/)
* class [PdfSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../pdfsaveoptions/)
* المجسم [Aspose.Words](../../../)


