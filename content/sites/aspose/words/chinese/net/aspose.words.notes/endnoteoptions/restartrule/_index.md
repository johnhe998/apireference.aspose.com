---
title: EndnoteOptions.RestartRule
second_title: Aspose.Words for .NET API 参考
description: EndnoteOptions 财产. 确定自动编号何时重新开始
type: docs
weight: 30
url: /zh/net/aspose.words.notes/endnoteoptions/restartrule/
---
## EndnoteOptions.RestartRule property

确定自动编号何时重新开始。

```csharp
public FootnoteNumberingRule RestartRule { get; set; }
```

### 评论

并非所有值都适用于尾注。 要确定哪些值适用，请参阅[`FootnoteNumberingRule`](../../footnotenumberingrule/).

### 例子

显示如何在文档中的某些位置重新开始脚注/尾注编号。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 脚注和尾注是一种将参考或旁注附加到文本的方法
// 这不会干扰主体文本的流动。 
// 插入脚注/尾注会添加一个小的上标参考符号
// 在我们插入脚注/尾注的主体文本处。
// 每个脚注/尾注还创建一个条目，其中包含一个与引用匹配的符号
// 主体文本中的符号。我们传递给文档构建器的“InsertEndnote”方法的参考文本。
// 默认情况下，脚注条目显示在包含
// 它们的参考符号和尾注出现在文档的末尾。
builder.Write("Text 1. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 1.");
builder.Write("Text 2. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 2.");
builder.InsertBreak(BreakType.PageBreak);
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 3.");
builder.Write("Text 4. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 4.");

builder.InsertBreak(BreakType.PageBreak);

builder.Write("Text 1. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 1.");
builder.Write("Text 2. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 2.");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 3.");
builder.Write("Text 4. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 4.");

// 默认情况下，每个脚注和尾注的引用符号是它的索引
// 在所有文档的脚注/尾注中。每个文档都有单独的计数
// 用于脚注和尾注，并且不会在任何时候重新开始这些计数。
Assert.AreEqual(doc.FootnoteOptions.RestartRule, FootnoteNumberingRule.Default);
Assert.AreEqual(FootnoteNumberingRule.Default, FootnoteNumberingRule.Continuous);

// 我们可以使用“RestartRule”属性来让文档重新启动
//脚注/尾注在新的页面或部分计数。
doc.FootnoteOptions.RestartRule = FootnoteNumberingRule.RestartPage;
doc.EndnoteOptions.RestartRule = FootnoteNumberingRule.RestartSection;

doc.Save(ArtifactsDir + "InlineStory.NumberingRule.docx");
```

### 也可以看看

* enum [FootnoteNumberingRule](../../footnotenumberingrule/)
* class [EndnoteOptions](../)
* 命名空间 [Aspose.Words.Notes](../../endnoteoptions/)
* 部件 [Aspose.Words](../../../)


