---
title: Footnote.Footnote
second_title: Aspose.Words for .NET API 参考
description: Footnote 构造函数. 初始化 脚注类.
type: docs
weight: 10
url: /zh/net/aspose.words.notes/footnote/footnote/
---
## Footnote constructor

初始化 **脚注**类.

```csharp
public Footnote(DocumentBase doc, FootnoteType footnoteType)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| doc | DocumentBase | 所有者文件。 |
| footnoteType | FootnoteType | 一个[`FootnoteType`](../footnotetype/) value 指定这是脚注还是尾注。 |

### 评论

什么时候 **脚注**被创建，它属于指定的文档，但不是 还不是文档的一部分，并且 **父节点**一片空白。

追加 **脚注**在要插入脚注的段落上使用 InsertAfter 或 InsertBefore 到文档中。

### 例子

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

* class [DocumentBase](../../../aspose.words/documentbase/)
* enum [FootnoteType](../../footnotetype/)
* class [Footnote](../)
* 命名空间 [Aspose.Words.Notes](../../footnote/)
* 部件 [Aspose.Words](../../../)


