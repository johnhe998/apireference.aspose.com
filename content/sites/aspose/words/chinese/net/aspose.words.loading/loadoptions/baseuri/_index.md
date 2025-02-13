---
title: LoadOptions.BaseUri
second_title: Aspose.Words for .NET API 参考
description: LoadOptions 财产. 获取或设置将用于在需要时将在文档中找到的相对 URI 解析为绝对 URI 的字符串 可以是 null 或空字符串默认为空
type: docs
weight: 20
url: /zh/net/aspose.words.loading/loadoptions/baseuri/
---
## LoadOptions.BaseUri property

获取或设置将用于在需要时将在文档中找到的相对 URI 解析为绝对 URI 的字符串。 可以是 null 或空字符串。默认为空。

```csharp
public string BaseUri { get; set; }
```

### 评论

在以下情况下，此属性用于将相对 URI 解析为绝对：

1. 当从流中加载 HTML 文档并且该文档包含具有 相对 URI 的图像并且没有在 BASE HTML 元素中指定的基本 URI 时。
2. 将文档保存为 PDF 和其他格式时，检索使用相对 URIs 链接的图像，以便将图像保存到输出文档中。

### 例子

演示如何使用基本 URI 打开包含来自流的图像的 HTML 文档。

```csharp
using (Stream stream = File.OpenRead(MyDir + "Document.html"))
{
    // 在加载时传递基本文件夹的 URI
    // 以便可以找到 HTML 文档中具有相对 URI 的任何图像。
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.BaseUri = ImageDir;

    Document doc = new Document(stream, loadOptions);

    // 验证文档的第一个形状是否包含有效图像。
    Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);

    Assert.IsTrue(shape.IsImage);
    Assert.IsNotNull(shape.ImageData.ImageBytes);
    Assert.AreEqual(32.0, ConvertUtil.PointToPixel(shape.Width), 0.01);
    Assert.AreEqual(32.0, ConvertUtil.PointToPixel(shape.Height), 0.01);
}
```

### 也可以看看

* class [LoadOptions](../)
* 命名空间 [Aspose.Words.Loading](../../loadoptions/)
* 部件 [Aspose.Words](../../../)


