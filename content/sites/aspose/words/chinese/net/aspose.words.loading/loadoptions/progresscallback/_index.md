---
title: LoadOptions.ProgressCallback
second_title: Aspose.Words for .NET API 参考
description: LoadOptions 财产. 在加载文档期间调用并接受有关加载进度的数据
type: docs
weight: 130
url: /zh/net/aspose.words.loading/loadoptions/progresscallback/
---
## LoadOptions.ProgressCallback property

在加载文档期间调用并接受有关加载进度的数据。

```csharp
public IDocumentLoadingCallback ProgressCallback { get; set; }
```

### 评论

Docx,FlatOpc,Docm,Dotm,Dotx,Markdown,Rtf,WordML,Doc,Dot,Odt,Ott支持的格式。

### 例子

显示如何在文档加载超出预期加载时间时通知用户。

```csharp
[Test]
public void ProgressCallback()
{
    LoadingProgressCallback progressCallback = new LoadingProgressCallback();

    LoadOptions loadOptions = new LoadOptions { ProgressCallback = progressCallback };

    try
    {
        Document doc = new Document(MyDir + "Big document.docx", loadOptions);
    }
    catch (OperationCanceledException exception)
    {
        Console.WriteLine(exception.Message);

        // 处理加载持续时间问题。
    }
}

/// <summary>
/// 在“MaxDuration”秒后取消文档加载。
/// </summary>
public class LoadingProgressCallback : IDocumentLoadingCallback
{
    /// <summary>
    /// 中心。
    /// </summary>
    public LoadingProgressCallback()
    {
        mLoadingStartedAt = DateTime.Now;
    }

    /// <summary>
    /// 文档加载过程中调用的回调方法。
    /// </summary>
    /// <param name="args">加载参数。</param>
    public void Notify(DocumentLoadingArgs args)
    {
        DateTime canceledAt = DateTime.Now;
        double ellapsedSeconds = (canceledAt - mLoadingStartedAt).TotalSeconds;

        if (ellapsedSeconds > MaxDuration)
            throw new OperationCanceledException($"EstimatedProgress = {args.EstimatedProgress}; CanceledAt = {canceledAt}");
    }

    /// <summary>
    /// 开始加载文档的日期和时间。
    /// </summary>
    private readonly DateTime mLoadingStartedAt;

    /// <summary>
    /// 允许的最大持续时间（以秒为单位）。
    /// </summary>
    private const double MaxDuration = 0.5;
}
```

### 也可以看看

* interface [IDocumentLoadingCallback](../../idocumentloadingcallback/)
* class [LoadOptions](../)
* 命名空间 [Aspose.Words.Loading](../../loadoptions/)
* 部件 [Aspose.Words](../../../)


