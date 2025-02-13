---
title: Enum FootnoteType
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Notes.FootnoteType 枚举. 指定这是脚注还是尾注
type: docs
weight: 4060
url: /zh/net/aspose.words.notes/footnotetype/
---
## FootnoteType enumeration

指定这是脚注还是尾注。

```csharp
public enum FootnoteType
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| Footnote | `0` | 对象是脚注。 |
| Endnote | `1` | 对象是尾注。 |

### 评论

脚注和尾注都由对象表示Footnote 类。利用[`FootnoteType`](../footnote/footnotetype/)区分脚注 和尾注。

### 例子

显示如何使用脚注和尾注引用文本。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 插入一些文本并用脚注标记它，默认情况下 IsAuto 属性设置为“true”，
// 所以正文中看到的标记将自动编号为“1”，
// 并且脚注将出现在页面底部。
builder.Write("This text will be referenced by a footnote.");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote comment regarding referenced text.");

// 插入更多文本并用带有自定义参考标记的尾注进行标记，
// 它将用于代替数字“2”并将“IsAuto”设置为 false。
builder.Write("This text will be referenced by an endnote.");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote comment regarding referenced text.", "CustomMark");

// 脚注总是出现在其引用文本的底部，
// 所以这个分页符不会影响脚注。
// 另一方面，尾注总是在文档的末尾
// 这样这个分页符会将尾注向下推到下一页。
builder.InsertBreak(BreakType.PageBreak);

doc.Save(ArtifactsDir + "DocumentBuilder.InsertFootnote.docx");
```

显示如何插入和自定义脚注。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 添加文本，并用脚注引用它。这个脚注将放置一个小的上标参考
// 在它引用的文本之后标记，并在页面底部的主体文本下方创建一个条目。
// 此条目将包含脚注的参考标记和参考文本，
// 我们将传递给文档构建器的“InsertFootnote”方法。
builder.Write("Main body text.");
Footnote footnote = builder.InsertFootnote(FootnoteType.Footnote, "Footnote text.");

// 如果这个属性设置为“true”，那么我们脚注的引用标记
// 将是它在所有部分脚注中的索引。
// 这是第一个脚注，所以引用标记为“1”。
Assert.True(footnote.IsAuto);

// 我们可以在脚注中移动文档构建器来编辑其参考文本。 
builder.MoveTo(footnote.FirstParagraph);
builder.Write(" More text added by a DocumentBuilder.");
builder.MoveToDocumentEnd();

Assert.AreEqual("\u0002 Footnote text. More text added by a DocumentBuilder.", footnote.GetText().Trim());

builder.Write(" More main body text.");
footnote = builder.InsertFootnote(FootnoteType.Footnote, "Footnote text.");

// 我们可以设置一个自定义引用标记，脚注将使用它而不是它的索引号。
footnote.ReferenceMark = "RefMark";

Assert.False(footnote.IsAuto);

// 将“IsAuto”标志设置为 true 的书签仍将显示其真实索引
// 即使以前的书签显示自定义参考标记，所以这个书签的参考标记将是“3”。
builder.Write(" More main body text.");
footnote = builder.InsertFootnote(FootnoteType.Footnote, "Footnote text.");

Assert.True(footnote.IsAuto);

doc.Save(ArtifactsDir + "InlineStory.AddFootnote.docx");
```

### 也可以看看

* 命名空间 [Aspose.Words.Notes](../../aspose.words.notes/)
* 部件 [Aspose.Words](../../)


