---
title: TextColumnCollection.Spacing
second_title: Aspose.Words for .NET API 参考
description: TextColumnCollection 财产. 当列均匀分布时获取或设置每列之间的空间量以点为单位
type: docs
weight: 50
url: /zh/net/aspose.words/textcolumncollection/spacing/
---
## TextColumnCollection.Spacing property

当列均匀分布时，获取或设置每列之间的空间量，以点为单位。

```csharp
public double Spacing { get; set; }
```

### 评论

只有在[`EvenlySpaced`](../evenlyspaced/)被设定为 **真的**.

### 例子

显示如何在一个部分中创建多个均匀间隔的列。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

TextColumnCollection columns = builder.PageSetup.TextColumns;
columns.Spacing = 100;
columns.SetCount(2);

builder.Writeln("Column 1.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Writeln("Column 2.");

doc.Save(ArtifactsDir + "PageSetup.ColumnsSameWidth.docx");
```

### 也可以看看

* class [TextColumnCollection](../)
* 命名空间 [Aspose.Words](../../textcolumncollection/)
* 部件 [Aspose.Words](../../../)


