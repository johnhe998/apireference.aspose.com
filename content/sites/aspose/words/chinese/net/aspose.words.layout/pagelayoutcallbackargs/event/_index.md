---
title: PageLayoutCallbackArgs.Event
second_title: Aspose.Words for .NET API 参考
description: PageLayoutCallbackArgs 财产. 获取事件
type: docs
weight: 20
url: /zh/net/aspose.words.layout/pagelayoutcallbackargs/event/
---
## PageLayoutCallbackArgs.Event property

获取事件。

```csharp
public PageLayoutEvent Event { get; }
```

### 例子

展示如何使用布局回调跟踪布局更改。

```csharp
[Test]
public void PageLayoutCallback()
{
    Document doc = new Document();
    doc.BuiltInDocumentProperties.Title = "My Document";

    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.Writeln("Hello world!");

    doc.LayoutOptions.Callback = new RenderPageLayoutCallback();
    doc.UpdatePageLayout();

    doc.Save(ArtifactsDir + "Layout.PageLayoutCallback.pdf");
}

/// <summary>
/// 当我们将文档保存为固定页面格式时通知我们
/// 并渲染一个页面，我们在本地文件系统中的图像上执行页面回流。
/// </summary>
private class RenderPageLayoutCallback : IPageLayoutCallback
{
    public void Notify(PageLayoutCallbackArgs a)
    {
        switch (a.Event)
        {
            case PageLayoutEvent.PartReflowFinished:
                NotifyPartFinished(a);
                break;
            case PageLayoutEvent.ConversionFinished:
                NotifyConversionFinished(a);
                break;
        }
    }

    private void NotifyPartFinished(PageLayoutCallbackArgs a)
    {
        Console.WriteLine($"Part at page {a.PageIndex + 1} reflow.");
        RenderPage(a, a.PageIndex);
    }

    private void NotifyConversionFinished(PageLayoutCallbackArgs a)
    {
        Console.WriteLine($"Document \"{a.Document.BuiltInDocumentProperties.Title}\" converted to page format.");
    }

    private void RenderPage(PageLayoutCallbackArgs a, int pageIndex)
    {
        ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png) { PageSet = new PageSet(pageIndex) };

        using (FileStream stream =
            new FileStream(ArtifactsDir + $@"PageLayoutCallback.page-{pageIndex + 1} {++mNum}.png",
                FileMode.Create))
            a.Document.Save(stream, saveOptions);
    }

    private int mNum;
}
```

### 也可以看看

* enum [PageLayoutEvent](../../pagelayoutevent/)
* class [PageLayoutCallbackArgs](../)
* 命名空间 [Aspose.Words.Layout](../../pagelayoutcallbackargs/)
* 部件 [Aspose.Words](../../../)


