---
title: IDocumentLoadingCallback.Notify
second_title: Aspose.Words for .NET API 参考
description: IDocumentLoadingCallback 方法. 调用此函数以通知文档加载进度
type: docs
weight: 10
url: /zh/net/aspose.words.loading/idocumentloadingcallback/notify/
---
## IDocumentLoadingCallback.Notify method

调用此函数以通知文档加载进度。

```csharp
public void Notify(DocumentLoadingArgs args)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| args | DocumentLoadingArgs | 事件的论据。 |

### 评论

此接口的主要用途是允许应用程序代码获取进度状态并中止加载过程。

应该从进度回调中抛出异常以进行中止，并且应该在消费者代码中捕获该异常。

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

* property [ProgressCallback](../../loadoptions/progresscallback/)
* class [DocumentLoadingArgs](../../documentloadingargs/)
* interface [IDocumentLoadingCallback](../)
* 命名空间 [Aspose.Words.Loading](../../idocumentloadingcallback/)
* 部件 [Aspose.Words](../../../)


