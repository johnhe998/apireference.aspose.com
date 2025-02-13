---
title: SaveOptions.UseHighQualityRendering
second_title: Aspose.Words for .NET API 参考
description: SaveOptions 财产. 获取或设置一个确定是否使用高质量即慢速渲染算法的值
type: docs
weight: 220
url: /zh/net/aspose.words.saving/saveoptions/usehighqualityrendering/
---
## SaveOptions.UseHighQualityRendering property

获取或设置一个确定是否使用高质量（即慢速）渲染算法的值。

```csharp
public bool UseHighQualityRendering { get; set; }
```

### 评论

默认值为`错误的`.

当文档导出为图像格式时使用此属性： Tiff,Png,BmpJpeg,Emf.

### 例子

演示如何使用 SaveOptions 提高呈现文档的质量。

```csharp
Document doc = new Document(MyDir + "Rendering.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Size = 60;
builder.Writeln("Some text.");

SaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

doc.Save(ArtifactsDir + "Document.ImageSaveOptions.Default.jpg", options);

options.UseAntiAliasing = true;
options.UseHighQualityRendering = true;

doc.Save(ArtifactsDir + "Document.ImageSaveOptions.HighQuality.jpg", options);
```

### 也可以看看

* class [SaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../saveoptions/)
* 部件 [Aspose.Words](../../../)


