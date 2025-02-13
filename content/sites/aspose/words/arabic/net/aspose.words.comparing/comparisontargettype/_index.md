---
title: Enum ComparisonTargetType
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Comparing.ComparisonTargetType تعداد. يسمح بتحديد المستند الأساسي الذي سيتم استخدامه أثناء المقارنة. القيمة الافتراضية هيCurrent .
type: docs
weight: 270
url: /ar/net/aspose.words.comparing/comparisontargettype/
---
## ComparisonTargetType enumeration

يسمح بتحديد المستند الأساسي الذي سيتم استخدامه أثناء المقارنة. القيمة الافتراضية هيCurrent .

```csharp
public enum ComparisonTargetType
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| Current | `0` | يتم استخدام هذا المستند كأساس أثناء المقارنة. |
| New | `1` | يتم استخدام مستند آخر كقاعدة أثناء المقارنة. |

### ملاحظات

يتعلق بخيار Microsoft Word "إظهار التغييرات في" في مربع الحوار "مقارنة المستندات".

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


