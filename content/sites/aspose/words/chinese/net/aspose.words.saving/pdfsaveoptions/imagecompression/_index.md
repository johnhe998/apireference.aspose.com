---
title: PdfSaveOptions.ImageCompression
second_title: Aspose.Words for .NET API 参考
description: PdfSaveOptions 财产. 指定用于文档中所有图像的压缩类型
type: docs
weight: 170
url: /zh/net/aspose.words.saving/pdfsaveoptions/imagecompression/
---
## PdfSaveOptions.ImageCompression property

指定用于文档中所有图像的压缩类型。

```csharp
public PdfImageCompression ImageCompression { get; set; }
```

### 评论

默认为Auto.

使用Jpeg让您可以通过[`JpegQuality`](../jpegquality/)财产。

使用Jpeg与其他压缩类型的性能相比， 提供了最快的转换速度，但在这种情况下，存在有损 JPEG 压缩。

使用Auto让我们通过控制输出文档中 Jpeg 的质量[`JpegQuality`](../jpegquality/)属性， ，但对于其他格式，原始像素数据通过Flate压缩提取并保存。 这种情况比Jpeg转换慢但无损。

### 例子

演示如何为我们要转换为 PDF 的文档中的所有图像指定压缩类型。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Jpeg image:");
builder.InsertImage(ImageDir + "Logo.jpg");
builder.InsertParagraph();
builder.Writeln("Png image:");
builder.InsertImage(ImageDir + "Transparent background logo.png");

// 创建一个“PdfSaveOptions”对象，我们可以将它传递给文档的“Save”方法
// 修改该方法如何将文档转换为 .PDF。
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();

// 将“ImageCompression”属性设置为“PdfImageCompression.Auto”以使用
// “ImageCompression” 属性来控制最终在输出 PDF 中的 Jpeg 图像的质量。
// 将“ImageCompression”属性设置为“PdfImageCompression.Jpeg”以使用
// “ImageCompression” 属性来控制最终在输出 PDF 中的所有图像的质量。
pdfSaveOptions.ImageCompression = pdfImageCompression;

// 将“JpegQuality”属性设置为“10”，以牺牲图像质量为代价加强压缩。
pdfSaveOptions.JpegQuality = 10;

doc.Save(ArtifactsDir + "PdfSaveOptions.ImageCompression.pdf", pdfSaveOptions);
```

### 也可以看看

* enum [PdfImageCompression](../../pdfimagecompression/)
* class [PdfSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../pdfsaveoptions/)
* 部件 [Aspose.Words](../../../)


