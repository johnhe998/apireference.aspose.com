---
title: GraphicsQualityOptions.TextRenderingHint
second_title: Aspose.Words for .NET API 参考
description: GraphicsQualityOptions 财产. 获取或设置与此 Graphics 关联的文本的呈现模式
type: docs
weight: 70
url: /zh/net/aspose.words.saving/graphicsqualityoptions/textrenderinghint/
---
## GraphicsQualityOptions.TextRenderingHint property

获取或设置与此 Graphics 关联的文本的呈现模式。

```csharp
public TextRenderingHint? TextRenderingHint { get; set; }
```

### 例子

展示如何在将文档转换为图像格式时设置渲染质量选项。

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

GraphicsQualityOptions qualityOptions = new GraphicsQualityOptions
{
    SmoothingMode = SmoothingMode.AntiAlias,
    TextRenderingHint = TextRenderingHint.ClearTypeGridFit,
    CompositingMode = CompositingMode.SourceOver,
    CompositingQuality = CompositingQuality.HighQuality,
    InterpolationMode = InterpolationMode.High,
    StringFormat = StringFormat.GenericTypographic
};

ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Jpeg);
saveOptions.GraphicsQualityOptions = qualityOptions;

doc.Save(ArtifactsDir + "ImageSaveOptions.GraphicsQuality.jpg", saveOptions);
```

### 也可以看看

* class [GraphicsQualityOptions](../)
* 命名空间 [Aspose.Words.Saving](../../graphicsqualityoptions/)
* 部件 [Aspose.Words](../../../)


