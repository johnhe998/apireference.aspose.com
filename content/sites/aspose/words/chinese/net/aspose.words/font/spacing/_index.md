---
title: Font.Spacing
second_title: Aspose.Words for .NET API 参考
description: Font 财产. 返回或设置字符之间的间距以磅为单位 .
type: docs
weight: 380
url: /zh/net/aspose.words/font/spacing/
---
## Font.Spacing property

返回或设置字符之间的间距（以磅为单位） .

```csharp
public double Spacing { get; set; }
```

### 例子

显示如何设置字符的水平缩放和间距。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 添加文本行并将字符宽度增加到 150%。
builder.Font.Scaling = 150;
builder.Writeln("Wide characters");

// 添加一行文本并在每个字符之间添加 1pt 的额外水平间距。
builder.Font.Spacing = 1;
builder.Writeln("Expanded by 1pt");

// 添加一行文本并将字符靠得更近 1pt。
builder.Font.Spacing = -1;
builder.Writeln("Condensed by 1pt");

doc.Save(ArtifactsDir + "Font.ScalingSpacing.docx");
```

### 也可以看看

* class [Font](../)
* 命名空间 [Aspose.Words](../../font/)
* 部件 [Aspose.Words](../../../)


