---
title: Font.SmallCaps
second_title: Aspose.Words for .NET API 参考
description: Font 财产. 如果字体格式为小写字母则为真
type: docs
weight: 360
url: /zh/net/aspose.words/font/smallcaps/
---
## Font.SmallCaps property

如果字体格式为小写字母，则为真。

```csharp
public bool SmallCaps { get; set; }
```

### 例子

显示如何格式化运行以大写显示其内容。

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);

// 有两种方法可以让运行以大写形式显示其小写文本而不更改内容。
// 1 - 设置 AllCaps 标志以以常规大写字母显示所有字符：
Run run = new Run(doc, "all capitals");
run.Font.AllCaps = true;
para.AppendChild(run);

para = (Paragraph)para.ParentNode.AppendChild(new Paragraph(doc));

// 2 - 设置 SmallCaps 标志以以小写字母显示所有字符：
// 如果一个字符是小写的，它将以大写形式出现
// 但将具有与小写相同的高度（字体的 x 高度）。
// 原来大写的字符看起来是一样的。
run = new Run(doc, "Small Capitals");
run.Font.SmallCaps = true;
para.AppendChild(run);

doc.Save(ArtifactsDir + "Font.Caps.docx");
```

### 也可以看看

* class [Font](../)
* 命名空间 [Aspose.Words](../../font/)
* 部件 [Aspose.Words](../../../)


