---
title: Class CompareOptions
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Comparing.CompareOptions 班级. 允许为文档比较操作选择高级选项
type: docs
weight: 260
url: /zh/net/aspose.words.comparing/compareoptions/
---
## CompareOptions class

允许为文档比较操作选择高级选项。

```csharp
public class CompareOptions
```

## 构造函数

| 姓名 | 描述 |
| --- | --- |
| [CompareOptions](compareoptions/)() | 默认构造函数。 |

## 特性

| 姓名 | 描述 |
| --- | --- |
| [Granularity](../../aspose.words.comparing/compareoptions/granularity/) { get; set; } | 指定是按字符还是按单词跟踪更改。 默认值为WordLevel. |
| [IgnoreCaseChanges](../../aspose.words.comparing/compareoptions/ignorecasechanges/) { get; set; } | True 表示文档比较不区分大小写。 默认比较区分大小写。 |
| [IgnoreComments](../../aspose.words.comparing/compareoptions/ignorecomments/) { get; set; } | 指定是否比较注释中的差异。 默认情况下不会忽略注释。 |
| [IgnoreDmlUniqueId](../../aspose.words.comparing/compareoptions/ignoredmluniqueid/) { get; set; } | 指定是否忽略 DrawingML 唯一 ID 中的差异。 默认值为 **错误的**. |
| [IgnoreFields](../../aspose.words.comparing/compareoptions/ignorefields/) { get; set; } | 指定是否比较字段的差异。 默认情况下不会忽略字段。 |
| [IgnoreFootnotes](../../aspose.words.comparing/compareoptions/ignorefootnotes/) { get; set; } | 指定是否比较脚注和尾注的差异。 默认不忽略脚注。 |
| [IgnoreFormatting](../../aspose.words.comparing/compareoptions/ignoreformatting/) { get; set; } | True 表示忽略格式化。 默认情况下不忽略文档格式。 |
| [IgnoreHeadersAndFooters](../../aspose.words.comparing/compareoptions/ignoreheadersandfooters/) { get; set; } | True 表示忽略页眉和页脚内容。 默认情况下不忽略页眉和页脚。 |
| [IgnoreTables](../../aspose.words.comparing/compareoptions/ignoretables/) { get; set; } | 指定是否比较表中包含的数据的差异。 默认情况下不会忽略表。 |
| [IgnoreTextboxes](../../aspose.words.comparing/compareoptions/ignoretextboxes/) { get; set; } | 指定是否比较文本框中包含的数据的差异。 默认情况下不会忽略文本框。 |
| [Target](../../aspose.words.comparing/compareoptions/target/) { get; set; } | 指定在比较期间应将哪个文档用作目标。 |

### 例子

显示如何在进行比较时过滤特定类型的文档元素。

```csharp
// 创建原始文档并用各种元素填充它。
Document docOriginal = new Document();
DocumentBuilder builder = new DocumentBuilder(docOriginal);

// 使用尾注引用的段落文本：
builder.Writeln("Hello world! This is the first paragraph.");
builder.InsertFootnote(FootnoteType.Endnote, "Original endnote text.");

// 桌子：
builder.StartTable();
builder.InsertCell();
builder.Write("Original cell 1 text");
builder.InsertCell();
builder.Write("Original cell 2 text");
builder.EndTable();

// 文本框：
Shape textBox = builder.InsertShape(ShapeType.TextBox, 150, 20);
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Original textbox contents");

// 日期字段：
builder.MoveTo(docOriginal.FirstSection.Body.AppendParagraph(""));
builder.InsertField(" DATE ");

// 评论：
Comment newComment = new Comment(docOriginal, "John Doe", "J.D.", DateTime.Now);
newComment.SetText("Original comment.");
builder.CurrentParagraph.AppendChild(newComment);

// 标题：
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Writeln("Original header contents.");

// 创建我们文档的克隆并对每个克隆文档的元素执行快速编辑。
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

// 比较文档会为已编辑文档中的每个编辑创建一个修订。
// CompareOptions 对象有一系列可以抑制修订的标志
// 在每种类型的元素上，有效地忽略它们的变化。
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

### 也可以看看

* 命名空间 [Aspose.Words.Comparing](../../aspose.words.comparing/)
* 部件 [Aspose.Words](../../)


