---
title: Document.LastSection
second_title: Aspose.Words for .NET API 参考
description: Document 财产. 获取文档的最后一节
type: docs
weight: 220
url: /zh/net/aspose.words/document/lastsection/
---
## Document.LastSection property

获取文档的最后一节。

```csharp
public Section LastSection { get; }
```

### 评论

返回`无效的`如果没有部分。

### 例子

显示如何使用文档构建器创建新部分。

```csharp
Document doc = new Document();

// 一个空白文档默认包含一个部分，
// 其中包含我们可以编辑的子节点。
Assert.AreEqual(1, doc.Sections.Count);

// 使用文档构建器将文本添加到第一部分。
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// 通过插入分节符创建第二个节。
builder.InsertBreak(BreakType.SectionBreakNewPage);

Assert.AreEqual(2, doc.Sections.Count);

// 每个部分都有自己的页面设置设置。
// 我们可以将第二部分的文本分成两列。
// 这不会影响第一部分的文本。
doc.LastSection.PageSetup.TextColumns.SetCount(2);
builder.Writeln("Column 1.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Writeln("Column 2.");

Assert.AreEqual(1, doc.FirstSection.PageSetup.TextColumns.Count);
Assert.AreEqual(2, doc.LastSection.PageSetup.TextColumns.Count);

doc.Save(ArtifactsDir + "Section.Create.docx");
```

### 也可以看看

* class [Section](../../section/)
* class [Document](../)
* 命名空间 [Aspose.Words](../../document/)
* 部件 [Aspose.Words](../../../)


