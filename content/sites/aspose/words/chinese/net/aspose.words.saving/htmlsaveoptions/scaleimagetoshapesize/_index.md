---
title: HtmlSaveOptions.ScaleImageToShapeSize
second_title: Aspose.Words for .NET API 参考
description: HtmlSaveOptions 财产. 指定在导出为 HTMLMHTML 或 EPUB 时图像是否由 Aspose.Words 缩放到边界形状大小 默认值为真的.
type: docs
weight: 450
url: /zh/net/aspose.words.saving/htmlsaveoptions/scaleimagetoshapesize/
---
## HtmlSaveOptions.ScaleImageToShapeSize property

指定在导出为 HTML、MHTML 或 EPUB 时，图像是否由 Aspose.Words 缩放到边界形状大小。 默认值为`真的`.

```csharp
public bool ScaleImageToShapeSize { get; set; }
```

### 评论

Microsoft Word 文档中的图像是一种形状。形状有大小，而 image 有自己的大小。尺寸没有直接联系。例如，图像可以是 1024x786 像素， ，但显示此图像的形状可以是 400x300 点。

为了在浏览器中显示图像，必须将其缩放到形状大小。 `ScaleImageToShapeSize`属性控制 image 发生缩放的位置：在导出到 HTML 期间在 Aspose.Words 中或在显示文档时在浏览器中。

什么时候`ScaleImageToShapeSize`是`真的` ，图像由 Aspose.Words 在导出到 HTML 期间使用高质量缩放进行缩放。什么时候`ScaleImageToShapeSize` 是`错误的`，图像以其原始大小输出，浏览器必须对其进行缩放。

通常，浏览器会进行快速且质量较差的缩放。因此，您通常会在浏览器中获得更好的 显示质量和更小的文件大小`ScaleImageToShapeSize`是`真的` 但更好的打印质量和更快的转换时`ScaleImageToShapeSize`是`错误的`.

### 例子

演示如何在保存为 .html 时禁用将图像缩放到其父形状尺寸。

```csharp
Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);

            // 插入一个包含图像的形状，然后使该形状比图像小得多。
#if NET48 || JAVA
            Image image = Image.FromFile(ImageDir + "Transparent background logo.png");

            Assert.AreEqual(400, image.Size.Width);
            Assert.AreEqual(400, image.Size.Height);
#elif NET5_0_OR_GREATER
            SKBitmap image = SKBitmap.Decode(ImageDir + "Transparent background logo.png");

            Assert.AreEqual(400, image.Width);
            Assert.AreEqual(400, image.Height);
#endif

            Shape imageShape = builder.InsertImage(image);
            imageShape.Width = 50;
            imageShape.Height = 50;

            // 将包含带有图像的形状的文档保存为 HTML 将在本地文件系统中创建一个图像文件
            // 对于每个这样的形状。输出的 HTML 文档将使用 <image>链接到并显示这些图像的标签。
            // 当我们将文档保存为 HTML 时，我们可以传递一个 SaveOptions 对象来确定
            // 是否将形状内部的所有图像缩放到其形状的大小。
            // 将“ScaleImageToShapeSize”标志设置为“true”将缩小每个图像
            // 调整到包含它的形状的大小，这样保存的图像就不会大于文档要求的大小。
            // 将“ScaleImageToShapeSize”标志设置为“false”将保留这些图像的原始尺寸，
            // 这将占用更多空间以换取保持图像质量。
            HtmlSaveOptions options = new HtmlSaveOptions { ScaleImageToShapeSize = scaleImageToShapeSize };

            doc.Save(ArtifactsDir + "HtmlSaveOptions.ScaleImageToShapeSize.html", options);

            FileInfo fileInfo = new FileInfo(ArtifactsDir + "HtmlSaveOptions.ScaleImageToShapeSize.001.png");

#if NET48 || JAVA
        if (scaleImageToShapeSize)
            Assert.That(3000, Is.AtLeast(fileInfo.Length));
        else
            Assert.That(20000, Is.LessThan(fileInfo.Length));
#elif NET5_0_OR_GREATER
        if (scaleImageToShapeSize)
            Assert.That(10000, Is.AtLeast(fileInfo.Length));
        else
            Assert.That(30000, Is.LessThan(fileInfo.Length));
#endif
```

### 也可以看看

* property [ImageResolution](../imageresolution/)
* class [HtmlSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../htmlsaveoptions/)
* 部件 [Aspose.Words](../../../)


