---
title: ImageSaveOptions.JpegQuality
second_title: Aspose.Words for .NET API 参考
description: ImageSaveOptions 财产. 获取或设置确定生成的 JPEG 图像质量的值
type: docs
weight: 70
url: /zh/net/aspose.words.saving/imagesaveoptions/jpegquality/
---
## ImageSaveOptions.JpegQuality property

获取或设置确定生成的 JPEG 图像质量的值。

```csharp
public int JpegQuality { get; set; }
```

### 评论

仅在保存为 JPEG 时有效。

以 JPEG 格式保存时，使用此属性获取或设置生成图像的质量。 值可能在 0 到 100 之间变化，其中 0 表示质量最差但压缩最大，100 表示质量最好但压缩最小。

默认值为 95。

### 例子

显示如何在将文档另存为 JPEG 时配置压缩。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertImage(ImageDir + "Logo.jpg");

// 创建一个“ImageSaveOptions”对象，我们可以将它传递给文档的“Save”方法
// 修改该方法将文档呈现为图像的方式。
ImageSaveOptions imageOptions = new ImageSaveOptions(SaveFormat.Jpeg);

// 将“JpegQuality”属性设置为“10”以在呈现文档时使用更强的压缩。
// 这将减小文档的文件大小，但图像会显示更突出的压缩伪影。
imageOptions.JpegQuality = 10;

doc.Save(ArtifactsDir + "ImageSaveOptions.JpegQuality.HighCompression.jpg", imageOptions);

Assert.That(20000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.JpegQuality.HighCompression.jpg").Length));

// 将“JpegQuality”属性设置为“100”以在渲染文档时使用较弱的压缩。
// 这将以增加文件大小为代价提高图像质量。
imageOptions.JpegQuality = 100;

doc.Save(ArtifactsDir + "ImageSaveOptions.JpegQuality.HighQuality.jpg", imageOptions);

Assert.That(60000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.JpegQuality.HighQuality.jpg").Length));
```

### 也可以看看

* class [ImageSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../imagesaveoptions/)
* 部件 [Aspose.Words](../../../)


