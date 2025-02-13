---
title: PageSetup.EndnoteOptions
second_title: Aspose.Words for .NET API 参考
description: PageSetup 财产. 提供控制本节尾注编号和定位的选项
type: docs
weight: 120
url: /zh/net/aspose.words/pagesetup/endnoteoptions/
---
## PageSetup.EndnoteOptions property

提供控制本节尾注编号和定位的选项。

```csharp
public EndnoteOptions EndnoteOptions { get; }
```

### 例子

显示如何配置影响节中脚注/尾注的选项。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Hello world!");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote reference text.");

// 配置第一节所有脚注从1开始重新编号
// 在每个新页面上，并直接显示在每个页面上的文本下方。
FootnoteOptions footnoteOptions = doc.Sections[0].PageSetup.FootnoteOptions;
footnoteOptions.Position = FootnotePosition.BeneathText;
footnoteOptions.RestartRule = FootnoteNumberingRule.RestartPage;
footnoteOptions.StartNumber = 1;

builder.Write(" Hello again.");
builder.InsertFootnote(FootnoteType.Footnote, "Endnote reference text.");

// 配置第一部分的所有尾注，以保持整个部分的连续计数，
// 从 1 开始。另外，将它们全部设置为在文档末尾显示为收集。
EndnoteOptions endnoteOptions = doc.Sections[0].PageSetup.EndnoteOptions;
endnoteOptions.Position = EndnotePosition.EndOfDocument;
endnoteOptions.RestartRule = FootnoteNumberingRule.Continuous;
endnoteOptions.StartNumber = 1;

doc.Save(ArtifactsDir + "PageSetup.FootnoteOptions.docx");
```

### 也可以看看

* class [EndnoteOptions](../../../aspose.words.notes/endnoteoptions/)
* class [PageSetup](../)
* 命名空间 [Aspose.Words](../../pagesetup/)
* 部件 [Aspose.Words](../../../)


