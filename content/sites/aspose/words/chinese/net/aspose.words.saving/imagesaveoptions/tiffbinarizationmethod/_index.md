---
title: ImageSaveOptions.TiffBinarizationMethod
second_title: Aspose.Words for .NET API 参考
description: ImageSaveOptions 财产. 获取或设置将图像转换为 1 bpp 格式时使用的方法 whenSaveFormat是 SaveFormat.Tiff 和 TiffCompression等于 TiffCompression.Ccitt3 或 TiffCompression.Ccitt4.
type: docs
weight: 160
url: /zh/net/aspose.words.saving/imagesaveoptions/tiffbinarizationmethod/
---
## ImageSaveOptions.TiffBinarizationMethod property

获取或设置将图像转换为 1 bpp 格式时使用的方法 when[`SaveFormat`](../saveformat/)是 SaveFormat.Tiff 和 [`TiffCompression`](../tiffcompression/)等于 TiffCompression.Ccitt3 或 TiffCompression.Ccitt4.

```csharp
public ImageBinarizationMethod TiffBinarizationMethod { get; set; }
```

### 评论

默认值为 ImageBinarizationMethod.Threshold。

### 例子

演示在使用 Floyd-Steinberg 方法渲染 TIFF 图像时如何设置 TIFF 二值化错误阈值。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
builder.Writeln("Hello world!");
builder.InsertImage(ImageDir + "Logo.jpg");

// 当我们将文档保存为 TIFF 时，我们可以将 SaveOptions 对象传递给
// 调整 Aspose.Words 在渲染此图像时将应用的抖动。
// “ThresholdForFloydSteinbergDithering”属性的默认值为 128。
// 较高的值往往会产生较暗的图像。
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Tiff)
{
    TiffCompression = TiffCompression.Ccitt3,
    TiffBinarizationMethod = ImageBinarizationMethod.FloydSteinbergDithering,
    ThresholdForFloydSteinbergDithering = 240
};

doc.Save(ArtifactsDir + "ImageSaveOptions.FloydSteinbergDithering.tiff", options);
```

### 也可以看看

* enum [ImageBinarizationMethod](../../imagebinarizationmethod/)
* class [ImageSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../imagesaveoptions/)
* 部件 [Aspose.Words](../../../)


