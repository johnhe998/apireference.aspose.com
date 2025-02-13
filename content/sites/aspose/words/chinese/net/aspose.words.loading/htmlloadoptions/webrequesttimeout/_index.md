---
title: HtmlLoadOptions.WebRequestTimeout
second_title: Aspose.Words for .NET API 参考
description: HtmlLoadOptions 财产. 在 Web 请求超时之前等待的毫秒数默认值为 100000 毫秒 100 秒
type: docs
weight: 70
url: /zh/net/aspose.words.loading/htmlloadoptions/webrequesttimeout/
---
## HtmlLoadOptions.WebRequestTimeout property

在 Web 请求超时之前等待的毫秒数。默认值为 100000 毫秒 （100 秒）。

```csharp
public int WebRequestTimeout { get; set; }
```

### 评论

在加载 HTML 和 MHTML 文档中链接的外部资源（图像、style 表格）时，Aspose.Words 等待响应的毫秒数。

### 例子

演示如何在加载包含通过 URL 链接的外部资源的文档时为 Web 请求设置时间限制。

```csharp
{
    // 创建一个新的 HtmlLoadOptions 对象并验证其对 Web 请求的超时阈值。
    HtmlLoadOptions options = new HtmlLoadOptions();

    // 当加载一个 Html 文档，其资源通过网址 URL 外部链接时，
    // Aspose.Words 将中止在此时间限制内无法获取资源的 Web 请求，以毫秒为单位。
    Assert.AreEqual(100000, options.WebRequestTimeout);

    // 设置一个WarningCallback，它将记录加载过程中发生的所有警告。
    ListDocumentWarnings warningCallback = new ListDocumentWarnings();
    options.WarningCallback = warningCallback;

    // 加载这样的文档并验证是否已创建带有图像数据的形状。
    // 这个链接的图像需要一个网络请求来加载，这必须在我们的时间限制内完成。
    string html = $@"
        <html>
            <img src=""{ImageUrl}"" alt=""Aspose logo"" style=""width:400px;height:400px;"">
        </html>
    ";

    // 设置不合理的超时限制并再次尝试加载文档。
    options.WebRequestTimeout = 0;
    Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), options);
    Assert.AreEqual(2, warningCallback.Warnings().Count);

    // 在时限内获取图片失败的web请求仍然会生成图片。
    // 但是，图像将是通常表示丢失图像的红色“x”。
    Shape imageShape = (Shape)doc.GetChild(NodeType.Shape, 0, true);
    Assert.AreEqual(924, imageShape.ImageData.ImageBytes.Length);

    // 我们还可以配置自定义回调以从超时的 Web 请求中获取任何警告。
    Assert.AreEqual(WarningSource.Html, warningCallback.Warnings()[0].Source);
    Assert.AreEqual(WarningType.DataLoss, warningCallback.Warnings()[0].WarningType);
    Assert.AreEqual($"Couldn't load a resource from \'{ImageUrl}\'.", warningCallback.Warnings()[0].Description);

    Assert.AreEqual(WarningSource.Html, warningCallback.Warnings()[1].Source);
    Assert.AreEqual(WarningType.DataLoss, warningCallback.Warnings()[1].WarningType);
    Assert.AreEqual("Image has been replaced with a placeholder.", warningCallback.Warnings()[1].Description);

    doc.Save(ArtifactsDir + "HtmlLoadOptions.WebRequestTimeout.docx");
}

/// <summary>
/// 将文档加载操作期间发生的所有警告存储在列表中。
/// </summary>
private class ListDocumentWarnings : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        mWarnings.Add(info);
    }

    public List<WarningInfo> Warnings() { 
        return mWarnings;
    }

    private readonly List<WarningInfo> mWarnings = new List<WarningInfo>();
}
```

### 也可以看看

* class [HtmlLoadOptions](../)
* 命名空间 [Aspose.Words.Loading](../../htmlloadoptions/)
* 部件 [Aspose.Words](../../../)


