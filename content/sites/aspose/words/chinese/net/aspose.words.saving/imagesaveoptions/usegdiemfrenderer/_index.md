---
title: ImageSaveOptions.UseGdiEmfRenderer
second_title: Aspose.Words for .NET API 参考
description: ImageSaveOptions 财产. 获取或设置一个值确定在保存到 EMF 时是使用 GDI 还是 Aspose.Words 图元文件渲染器
type: docs
weight: 180
url: /zh/net/aspose.words.saving/imagesaveoptions/usegdiemfrenderer/
---
## ImageSaveOptions.UseGdiEmfRenderer property

获取或设置一个值，确定在保存到 EMF 时是使用 GDI+ 还是 Aspose.Words 图元文件渲染器。

```csharp
public bool UseGdiEmfRenderer { get; set; }
```

### 评论

如果设置为`真的`使用 GDI+ 图元文件渲染器。即内容写入 GDI+ graphics 对象并保存到元文件。

如果设置为`错误的`使用 Aspose.Words 元文件渲染器。即内容直接用Aspose.Words写入 元文件格式。

仅在保存到 EMF 时有效。

GDI+ 保存仅适用于 .NET。

默认值为`真的`.

### 例子

显示在将文档转换为 .emf 时如何选择渲染器。

```csharp
Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);

            builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
            builder.Writeln("Hello world!");
            builder.InsertImage(ImageDir + "Logo.jpg");

            // 当我们将文档保存为 EMF 图像时，我们可以传递一个 SaveOptions 对象来为图像选择一个渲染器。
            // 如果我们将“UseGdiEmfRenderer”标志设置为“true”，Aspose.Words 将使用 GDI+ 渲染器。
            // 如果我们将“UseGdiEmfRenderer”标志设置为“false”，Aspose.Words 将使用它自己的元文件渲染器。
            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Emf);
            saveOptions.UseGdiEmfRenderer = useGdiEmfRenderer;

            doc.Save(ArtifactsDir + "ImageSaveOptions.Renderer.emf", saveOptions);

            // GDI+ 渲染器通常会创建较大的文件。
            if (useGdiEmfRenderer)
#if NET48 || JAVA
                Assert.That(300000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.Renderer.emf").Length));
#elif NET5_0_OR_GREATER
                Assert.That(30000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.Renderer.emf").Length));
#endif
            else
                Assert.That(30000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.Renderer.emf").Length));
```

### 也可以看看

* class [ImageSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../imagesaveoptions/)
* 部件 [Aspose.Words](../../../)


