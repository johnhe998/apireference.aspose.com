---
title: SvgSaveOptions.TextOutputMode
second_title: Aspose.Words for .NET API 参考
description: SvgSaveOptions 财产. 获取或设置一个值确定在 SVG 中应如何呈现文本
type: docs
weight: 90
url: /zh/net/aspose.words.saving/svgsaveoptions/textoutputmode/
---
## SvgSaveOptions.TextOutputMode property

获取或设置一个值，确定在 SVG 中应如何呈现文本。

```csharp
public SvgTextOutputMode TextOutputMode { get; set; }
```

### 评论

使用此属性获取或设置在以 SVG 格式保存时文档中的文本应如何呈现 的模式。

默认值为UseTargetMachineFonts.

### 例子

演示如何在将 .docx 文档转换为 .svg 时模拟图像的属性。

```csharp
Document doc = new Document(MyDir + "Document.docx");

// 将 SvgSaveOptions 对象配置为没有页面边框或可选文本的保存。
SvgSaveOptions options = new SvgSaveOptions
{
    FitToViewPort = true,
    ShowPageBorder = false,
    TextOutputMode = SvgTextOutputMode.UsePlacedGlyphs
};

doc.Save(ArtifactsDir + "SvgSaveOptions.SaveLikeImage.svg", options);
```

### 也可以看看

* enum [SvgTextOutputMode](../../svgtextoutputmode/)
* class [SvgSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../svgsaveoptions/)
* 部件 [Aspose.Words](../../../)


