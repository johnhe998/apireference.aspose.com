---
title: Class DownsampleOptions
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Saving.DownsampleOptions 班级. 允许指定下采样选项
type: docs
weight: 4710
url: /zh/net/aspose.words.saving/downsampleoptions/
---
## DownsampleOptions class

允许指定下采样选项。

```csharp
public class DownsampleOptions
```

## 构造函数

| 姓名 | 描述 |
| --- | --- |
| [DownsampleOptions](downsampleoptions/)() | 默认构造函数。 |

## 特性

| 姓名 | 描述 |
| --- | --- |
| [DownsampleImages](../../aspose.words.saving/downsampleoptions/downsampleimages/) { get; set; } | 指定是否应该对图像进行下采样。 |
| [Resolution](../../aspose.words.saving/downsampleoptions/resolution/) { get; set; } | 指定图像应该被下采样到的分辨率（以每英寸像素为单位）。 |
| [ResolutionThreshold](../../aspose.words.saving/downsampleoptions/resolutionthreshold/) { get; set; } | 以每英寸像素为单位指定阈值分辨率。 如果文档中图像的分辨率小于阈值， 将不应用下采样算法。 值 0 表示不使用阈值检查，所有图像可以缩小尺寸被下采样。 |

### 例子

显示如何更改 PDF 文档中图像的分辨率。

```csharp
Document doc = new Document(MyDir + "Images.docx");

// 创建一个“PdfSaveOptions”对象，我们可以将它传递给文档的“Save”方法
// 修改该方法如何将文档转换为 .PDF。
PdfSaveOptions options = new PdfSaveOptions();

// 默认情况下，Aspose.Words 将我们保存为 PDF 的文档中的所有图像下采样到 220 ppi。
Assert.True(options.DownsampleOptions.DownsampleImages);
Assert.AreEqual(220, options.DownsampleOptions.Resolution);
Assert.AreEqual(0, options.DownsampleOptions.ResolutionThreshold);

doc.Save(ArtifactsDir + "PdfSaveOptions.DownsampleOptions.Default.pdf", options);

// 将“分辨率”属性设置为“36”以将所有图像下采样到 36 ppi。
options.DownsampleOptions.Resolution = 36;

// 将“ResolutionThreshold”属性设置为仅应用下采样
// 分辨率高于 128 ppi 的图像。
options.DownsampleOptions.ResolutionThreshold = 128;

// 在这个阶段，只有文档中的前两个图像会被下采样。
doc.Save(ArtifactsDir + "PdfSaveOptions.DownsampleOptions.LowerResolution.pdf", options);
```

### 也可以看看

* 命名空间 [Aspose.Words.Saving](../../aspose.words.saving/)
* 部件 [Aspose.Words](../../)


