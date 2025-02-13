---
title: FootnoteOptions.Columns
second_title: Aspose.Words for .NET API 参考
description: FootnoteOptions 财产. 指定用于格式化脚注区域的列数
type: docs
weight: 10
url: /zh/net/aspose.words.notes/footnoteoptions/columns/
---
## FootnoteOptions.Columns property

指定用于格式化脚注区域的列数。

```csharp
public int Columns { get; set; }
```

### 评论

如果此属性的值为 0，则脚注区域将根据 显示页面上的列数来格式化列数。默认值为 0.

### 例子

显示如何将脚注部分拆分为给定数量的列。

```csharp
Document doc = new Document(MyDir + "Footnotes and endnotes.docx");
doc.FootnoteOptions.Columns = 2;
doc.Save(ArtifactsDir + "Document.FootnoteColumns.docx");
```

### 也可以看看

* class [FootnoteOptions](../)
* 命名空间 [Aspose.Words.Notes](../../footnoteoptions/)
* 部件 [Aspose.Words](../../../)


