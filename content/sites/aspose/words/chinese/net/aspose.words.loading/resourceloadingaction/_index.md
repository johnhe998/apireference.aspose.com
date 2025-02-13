---
title: Enum ResourceLoadingAction
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Loading.ResourceLoadingAction 枚举. 指定资源加载的模式
type: docs
weight: 3480
url: /zh/net/aspose.words.loading/resourceloadingaction/
---
## ResourceLoadingAction enumeration

指定资源加载的模式。

```csharp
public enum ResourceLoadingAction
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| Default | `0` | Aspose.Words 将照常加载此资源。 |
| Skip | `1` | Aspose.Words 将跳过加载此资源。 只为图像存储没有数据的链接，HTML 格式将忽略 CSS 样式表。 |
| UserProvided | `2` | Aspose.Words 将使用用户提供的字节数组[`SetData`](../resourceloadingargs/setdata/)作为资源数据。 |

### 例子

展示如何自定义将外部资源加载到文档中的过程。

```csharp
{
    Document doc = new Document();
    doc.ResourceLoadingCallback = new ImageNameHandler();

    DocumentBuilder builder = new DocumentBuilder(doc);

    // 通常使用 URI 或字节数组插入图像。
    // 每个资源加载实例都会调用我们回调的 ResourceLoading 方法。
    builder.InsertImage("Google logo");
    builder.InsertImage("Aspose logo");
    builder.InsertImage("Watermark");

    Assert.AreEqual(3, doc.GetChildNodes(NodeType.Shape, true).Count);

    doc.Save(ArtifactsDir + "DocumentBase.ResourceLoadingCallback.docx");

/// <summary>
/// 允许我们使用预定义的速记而不是 URI 将图像加载到文档中。
/// 这会将图像加载逻辑与文档构建的其余部分分开。
/// </summary>
private class ImageNameHandler : IResourceLoadingCallback
{
    public ResourceLoadingAction ResourceLoading(ResourceLoadingArgs args)
    {
        // 如果此回调在加载图像时遇到图像速记之一，
        // 它将为每个定义的速记应用唯一的逻辑，而不是将其视为 URI。
        if (args.ResourceType == ResourceType.Image)
            switch (args.OriginalUri)
            {
                case "Google logo":
                    using (WebClient webClient = new WebClient())
                    {
                        args.SetData(webClient.DownloadData("http://www.google.com/images/logos/ps_logo2.png"));
                    }

                    return ResourceLoadingAction.UserProvided;

                case "Aspose logo":
                    args.SetData(File.ReadAllBytes(ImageDir + "Logo.jpg"));

                    return ResourceLoadingAction.UserProvided;

                case "Watermark":
                    args.SetData(File.ReadAllBytes(ImageDir + "Transparent background logo.png"));

                    return ResourceLoadingAction.UserProvided;
            }

        return ResourceLoadingAction.Default;
    }
}
```

### 也可以看看

* 命名空间 [Aspose.Words.Loading](../../aspose.words.loading/)
* 部件 [Aspose.Words](../../)


