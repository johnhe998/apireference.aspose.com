---
title: GraphicsQualityOptions.StringFormat
second_title: Aspose.Words for .NET API 参考
description: GraphicsQualityOptions 财产. 获取或设置文本布局信息例如对齐方向和制表位显示操作 例如省略号插入和国家数字替换和 OpenType 功能
type: docs
weight: 60
url: /zh/net/aspose.words.saving/graphicsqualityoptions/stringformat/
---
## GraphicsQualityOptions.StringFormat property

获取或设置文本布局信息（例如对齐、方向和制表位）显示操作 （例如省略号插入和国家数字替换）和 OpenType 功能。

```csharp
public StringFormat StringFormat { get; set; }
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


