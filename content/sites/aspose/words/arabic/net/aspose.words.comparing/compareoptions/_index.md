---
title: Class CompareOptions
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Comparing.CompareOptions فصل. يسمح باختيار الخيارات المتقدمة لعملية مقارنة المستندات.
type: docs
weight: 260
url: /ar/net/aspose.words.comparing/compareoptions/
---
## CompareOptions class

يسمح باختيار الخيارات المتقدمة لعملية مقارنة المستندات.

```csharp
public class CompareOptions
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [CompareOptions](compareoptions/)() | Default_Constructor |

## الخصائص

| اسم | وصف |
| --- | --- |
| [Granularity](../../aspose.words.comparing/compareoptions/granularity/) { get; set; } | يحدد ما إذا كان يتم تعقب التغييرات بالحرف أو بالكلمة. القيمة الافتراضية هيWordLevel . |
| [IgnoreCaseChanges](../../aspose.words.comparing/compareoptions/ignorecasechanges/) { get; set; } | يشير True إلى أن مقارنة المستندات غير حساسة لحالة الأحرف. تعتبر المقارنة الافتراضية حساسة لحالة الأحرف. |
| [IgnoreComments](../../aspose.words.comparing/compareoptions/ignorecomments/) { get; set; } | تحديد ما إذا كان سيتم مقارنة الاختلافات في التعليقات. لا يتم تجاهل التعليقات افتراضيًا. |
| [IgnoreDmlUniqueId](../../aspose.words.comparing/compareoptions/ignoredmluniqueid/) { get; set; } | يحدد ما إذا كان سيتم تجاهل الاختلاف في معرّف DrawingML الفريد. القيمة الافتراضية هي **خاطئة** . |
| [IgnoreFields](../../aspose.words.comparing/compareoptions/ignorefields/) { get; set; } | تحديد ما إذا كان سيتم مقارنة الاختلافات في الحقول. لا يتم تجاهل الحقول افتراضيًا. |
| [IgnoreFootnotes](../../aspose.words.comparing/compareoptions/ignorefootnotes/) { get; set; } | تحديد ما إذا كان سيتم مقارنة الاختلافات في الحواشي السفلية والتعليقات الختامية. لا يتم تجاهل الحواشي السفلية افتراضيًا. |
| [IgnoreFormatting](../../aspose.words.comparing/compareoptions/ignoreformatting/) { get; set; } | صحيح يشير إلى أنه تم تجاهل التنسيق. لا يتم تجاهل تنسيق المستند الافتراضي. |
| [IgnoreHeadersAndFooters](../../aspose.words.comparing/compareoptions/ignoreheadersandfooters/) { get; set; } | تشير True إلى أنه يتم تجاهل محتوى الرؤوس والتذييلات. لا يتم تجاهل الرؤوس والتذييلات بشكل افتراضي. |
| [IgnoreTables](../../aspose.words.comparing/compareoptions/ignoretables/) { get; set; } | تحديد ما إذا كان سيتم مقارنة الاختلافات في البيانات الموجودة في الجداول. لا يتم تجاهل الجداول الافتراضية . |
| [IgnoreTextboxes](../../aspose.words.comparing/compareoptions/ignoretextboxes/) { get; set; } | تحديد ما إذا كان سيتم مقارنة الاختلافات في البيانات الموجودة داخل مربعات النص. لا يتم تجاهل مربعات النص افتراضيًا. |
| [Target](../../aspose.words.comparing/compareoptions/target/) { get; set; } | يحدد المستند الذي يجب استخدامه كهدف أثناء المقارنة. |

### أمثلة

يوضح كيفية تصفية أنواع معينة من عناصر المستند عند إجراء مقارنة.

```csharp
// أنشئ المستند الأصلي واملأه بأنواع مختلفة من العناصر.
Document docOriginal = new Document();
DocumentBuilder builder = new DocumentBuilder(docOriginal);

// نص فقرة مشار إليه بتعليق ختامي:
builder.Writeln("Hello world! This is the first paragraph.");
builder.InsertFootnote(FootnoteType.Endnote, "Original endnote text.");

// الطاولة:
builder.StartTable();
builder.InsertCell();
builder.Write("Original cell 1 text");
builder.InsertCell();
builder.Write("Original cell 2 text");
builder.EndTable();

// مربع الكتابة:
Shape textBox = builder.InsertShape(ShapeType.TextBox, 150, 20);
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Original textbox contents");

// حقل التاريخ:
builder.MoveTo(docOriginal.FirstSection.Body.AppendParagraph(""));
builder.InsertField(" DATE ");

// تعليق:
Comment newComment = new Comment(docOriginal, "John Doe", "J.D.", DateTime.Now);
newComment.SetText("Original comment.");
builder.CurrentParagraph.AppendChild(newComment);

// العنوان:
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Writeln("Original header contents.");

// قم بإنشاء نسخة من وثيقتنا وقم بإجراء تعديل سريع على كل عنصر من عناصر المستند المنسوخ.
Document docEdited = (Document)docOriginal.Clone(true);
Paragraph firstParagraph = docEdited.FirstSection.Body.FirstParagraph;

firstParagraph.Runs[0].Text = "hello world! this is the first paragraph, after editing.";
firstParagraph.ParagraphFormat.Style = docEdited.Styles[StyleIdentifier.Heading1];
((Footnote)docEdited.GetChild(NodeType.Footnote, 0, true)).FirstParagraph.Runs[1].Text = "Edited endnote text.";
((Table)docEdited.GetChild(NodeType.Table, 0, true)).FirstRow.Cells[1].FirstParagraph.Runs[0].Text = "Edited Cell 2 contents";
((Shape)docEdited.GetChild(NodeType.Shape, 0, true)).FirstParagraph.Runs[0].Text = "Edited textbox contents";
((FieldDate)docEdited.Range.Fields[0]).UseLunarCalendar = true; 
((Comment)docEdited.GetChild(NodeType.Comment, 0, true)).FirstParagraph.Runs[0].Text = "Edited comment.";
docEdited.FirstSection.HeadersFooters[HeaderFooterType.HeaderPrimary].FirstParagraph.Runs[0].Text =
    "Edited header contents.";

// تؤدي المقارنة بين المستندات إلى إنشاء مراجعة لكل تحرير في المستند المحرر.
// يحتوي كائن CompareOptions على سلسلة من العلامات التي يمكنها منع المراجعات
// على كل نوع من العناصر ، متجاهلاً تغييرها بشكل فعال.
Aspose.Words.Comparing.CompareOptions compareOptions = new Aspose.Words.Comparing.CompareOptions();
compareOptions.IgnoreFormatting = false;
compareOptions.IgnoreCaseChanges = false;
compareOptions.IgnoreComments = false;
compareOptions.IgnoreTables = false;
compareOptions.IgnoreFields = false;
compareOptions.IgnoreFootnotes = false;
compareOptions.IgnoreTextboxes = false;
compareOptions.IgnoreHeadersAndFooters = false;
compareOptions.Target = ComparisonTargetType.New;

docOriginal.Compare(docEdited, "John Doe", DateTime.Now, compareOptions);
docOriginal.Save(ArtifactsDir + "Document.CompareOptions.docx");
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Comparing](../../aspose.words.comparing/)
* المجسم [Aspose.Words](../../)


