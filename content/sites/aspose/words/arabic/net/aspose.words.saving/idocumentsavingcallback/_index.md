---
title: Interface IDocumentSavingCallback
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Saving.IDocumentSavingCallback واجهه المستخدم. قم بتنفيذ هذه الواجهة إذا كنت تريد استدعاء طريقتك المخصصة أثناء حفظ المستند.
type: docs
weight: 4890
url: /ar/net/aspose.words.saving/idocumentsavingcallback/
---
## IDocumentSavingCallback interface

قم بتنفيذ هذه الواجهة إذا كنت تريد استدعاء طريقتك المخصصة أثناء حفظ المستند.

```csharp
public interface IDocumentSavingCallback
```

## طُرق

| اسم | وصف |
| --- | --- |
| [Notify](../../aspose.words.saving/idocumentsavingcallback/notify/)(DocumentSavingArgs) | يسمى هذا للإبلاغ عن تقدم حفظ المستندات. |

### أمثلة

يوضح كيفية إدارة مستند أثناء الحفظ في html.

```csharp
public void ProgressCallback(SaveFormat saveFormat, string ext)
{
    Document doc = new Document(MyDir + "Big document.docx");

    // يتم دعم التنسيقات التالية: Html و Mhtml و Epub.
    HtmlSaveOptions saveOptions = new HtmlSaveOptions(saveFormat)
    {
        ProgressCallback = new SavingProgressCallback()
    };

    var exception = Assert.Throws<OperationCanceledException>(() =>
        doc.Save(ArtifactsDir + $"HtmlSaveOptions.ProgressCallback.{ext}", saveOptions));
    Assert.True(exception?.Message.Contains("EstimatedProgress"));
}

/// <summary>
/// حفظ رد الاتصال التقدم. إلغاء حفظ مستند بعد "MaxDuration" ثواني.
/// </summary>
public class SavingProgressCallback : IDocumentSavingCallback
{
    /// <summary>
    /// تحكم.
    /// </summary>
    public SavingProgressCallback()
    {
        mSavingStartedAt = DateTime.Now;
    }

    /// <summary>
    /// طريقة رد الاتصال التي تم استدعاؤها أثناء حفظ المستند.
    /// </summary>
    /// < param name = "args" > حفظ الوسائط. < / param >
    public void Notify(DocumentSavingArgs args)
    {
        DateTime canceledAt = DateTime.Now;
        double ellapsedSeconds = (canceledAt - mSavingStartedAt).TotalSeconds;
        if (ellapsedSeconds > MaxDuration)
            throw new OperationCanceledException($"EstimatedProgress = {args.EstimatedProgress}; CanceledAt = {canceledAt}");
    }

    /// <summary>
    /// تاريخ ووقت بدء حفظ المستند.
    /// </summary>
    private readonly DateTime mSavingStartedAt;

    /// <summary>
    /// أقصى مدة مسموح بها بالثانية.
    /// </summary>
    private const double MaxDuration = 0.1d;
}
```

يوضح كيفية إدارة مستند أثناء الحفظ في docx.

```csharp
public void ProgressCallback(SaveFormat saveFormat, string ext)
{
    Document doc = new Document(MyDir + "Big document.docx");

    // يتم دعم التنسيقات التالية: Docx و FlatOpc و Docm و Dotm و Dotx.
    OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(saveFormat)
    {
        ProgressCallback = new SavingProgressCallback()
    };

    var exception = Assert.Throws<OperationCanceledException>(() =>
        doc.Save(ArtifactsDir + $"OoxmlSaveOptions.ProgressCallback.{ext}", saveOptions));
    Assert.True(exception?.Message.Contains("EstimatedProgress"));
}

/// <summary>
/// حفظ رد الاتصال التقدم. إلغاء حفظ مستند بعد "MaxDuration" ثواني.
/// </summary>
public class SavingProgressCallback : IDocumentSavingCallback
{
    /// <summary>
    /// تحكم.
    /// </summary>
    public SavingProgressCallback()
    {
        mSavingStartedAt = DateTime.Now;
    }

    /// <summary>
    /// طريقة رد الاتصال التي تم استدعاؤها أثناء حفظ المستند.
    /// </summary>
    /// < param name = "args" > حفظ الوسائط. < / param >
    public void Notify(DocumentSavingArgs args)
    {
        DateTime canceledAt = DateTime.Now;
        double ellapsedSeconds = (canceledAt - mSavingStartedAt).TotalSeconds;
        if (ellapsedSeconds > MaxDuration)
            throw new OperationCanceledException($"EstimatedProgress = {args.EstimatedProgress}; CanceledAt = {canceledAt}");
    }

    /// <summary>
    /// تاريخ ووقت بدء حفظ المستند.
    /// </summary>
    private readonly DateTime mSavingStartedAt;

    /// <summary>
    /// أقصى مدة مسموح بها بالثانية.
    /// </summary>
    private const double MaxDuration = 0.01d;
}
```

يوضح كيفية إدارة مستند أثناء الحفظ في xamlflow.

```csharp
public void ProgressCallback(SaveFormat saveFormat, string ext)
{
    Document doc = new Document(MyDir + "Big document.docx");

    // يتم دعم التنسيقات التالية: XamlFlow و XamlFlowPack.
    XamlFlowSaveOptions saveOptions = new XamlFlowSaveOptions(saveFormat)
    {
        ProgressCallback = new SavingProgressCallback()
    };

    var exception = Assert.Throws<OperationCanceledException>(() =>
        doc.Save(ArtifactsDir + $"XamlFlowSaveOptions.ProgressCallback.{ext}", saveOptions));
    Assert.True(exception?.Message.Contains("EstimatedProgress"));
}

/// <summary>
/// حفظ رد الاتصال التقدم. إلغاء حفظ مستند بعد "MaxDuration" ثواني.
/// </summary>
public class SavingProgressCallback : IDocumentSavingCallback
{
    /// <summary>
    /// تحكم.
    /// </summary>
    public SavingProgressCallback()
    {
        mSavingStartedAt = DateTime.Now;
    }

    /// <summary>
    /// طريقة رد الاتصال التي تم استدعاؤها أثناء حفظ المستند.
    /// </summary>
    /// < param name = "args" > حفظ الوسائط. < / param >
    public void Notify(DocumentSavingArgs args)
    {
        DateTime canceledAt = DateTime.Now;
        double ellapsedSeconds = (canceledAt - mSavingStartedAt).TotalSeconds;
        if (ellapsedSeconds > MaxDuration)
            throw new OperationCanceledException($"EstimatedProgress = {args.EstimatedProgress}; CanceledAt = {canceledAt}");
    }

    /// <summary>
    /// تاريخ ووقت بدء حفظ المستند.
    /// </summary>
    private readonly DateTime mSavingStartedAt;

    /// <summary>
    /// أقصى مدة مسموح بها بالثانية.
    /// </summary>
    private const double MaxDuration = 0.01d;
}
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Saving](../../aspose.words.saving/)
* المجسم [Aspose.Words](../../)


