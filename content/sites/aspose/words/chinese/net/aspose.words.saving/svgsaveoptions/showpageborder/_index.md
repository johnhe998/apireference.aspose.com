---
title: SvgSaveOptions.ShowPageBorder
second_title: Aspose.Words for .NET API 参考
description: SvgSaveOptions 财产. 控制是否在页面轮廓中添加边框 默认为真的.
type: docs
weight: 80
url: /zh/net/aspose.words.saving/svgsaveoptions/showpageborder/
---
## SvgSaveOptions.ShowPageBorder property

控制是否在页面轮廓中添加边框。 默认为`真的`.

```csharp
public bool ShowPageBorder { get; set; }
```

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

* class [SvgSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../svgsaveoptions/)
* 部件 [Aspose.Words](../../../)


