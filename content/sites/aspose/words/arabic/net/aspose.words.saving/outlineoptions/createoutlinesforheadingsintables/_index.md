---
title: OutlineOptions.CreateOutlinesForHeadingsInTables
second_title: Aspose.Words لمراجع .NET API
description: OutlineOptions ملكية. يحدد ما إذا كان سيتم إنشاء مخططات تفصيلية للعناوين فقرات منسقة باستخدام أنماط العناوين داخل الجداول.
type: docs
weight: 40
url: /ar/net/aspose.words.saving/outlineoptions/createoutlinesforheadingsintables/
---
## OutlineOptions.CreateOutlinesForHeadingsInTables property

يحدد ما إذا كان سيتم إنشاء مخططات تفصيلية للعناوين (فقرات منسقة باستخدام أنماط العناوين) داخل الجداول.

```csharp
public bool CreateOutlinesForHeadingsInTables { get; set; }
```

### ملاحظات

القيمة الافتراضية هي **خاطئة**.

### أمثلة

يوضح كيفية إنشاء مدخلات مخطط مستند PDF للعناوين داخل الجداول.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// قم بإنشاء جدول من ثلاثة صفوف. الصف الأول
// الذي سنقوم بتنسيق نصه بأسلوب نوع العنوان ، سيكون بمثابة رأس العمود.
builder.StartTable();
builder.InsertCell();
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Write("Customers");
builder.EndRow();
builder.InsertCell();
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Normal;
builder.Write("John Doe");
builder.EndRow();
builder.InsertCell();
builder.Write("Jane Doe");
builder.EndTable();

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();

// سيحتوي مستند PDF الناتج على مخطط تفصيلي ، وهو جدول محتويات يسرد العناوين في نص المستند.
// سيأخذنا النقر فوق إدخال في هذا المخطط التفصيلي إلى موقع العنوان الخاص به.
// اضبط خاصية "HeadingsOutlineLevels" على "1" للحصول على المخطط التفصيلي
// لتسجيل العناوين بمستويات عناوين لا تزيد عن 1.
pdfSaveOptions.OutlineOptions.HeadingsOutlineLevels = 1;

// اضبط خاصية "CreateOutlinesForHeadingsInTables" على "false" لاستبعاد جميع العناوين داخل الجداول ،
// مثل الذي أنشأناه أعلاه من المخطط التفصيلي.
// قم بتعيين خاصية "CreateOutlinesForHeadingsInTables" على "true" لتضمين جميع العناوين داخل الجداول
// في المخطط التفصيلي ، بشرط أن يكون لديهم مستوى عنوان لا يزيد عن قيمة خاصية "HeadingsOutlineLevels".
pdfSaveOptions.OutlineOptions.CreateOutlinesForHeadingsInTables = createOutlinesForHeadingsInTables;

doc.Save(ArtifactsDir + "PdfSaveOptions.TableHeadingOutlines.pdf", pdfSaveOptions);
```

### أنظر أيضا

* class [OutlineOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../outlineoptions/)
* المجسم [Aspose.Words](../../../)


