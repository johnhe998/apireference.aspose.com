---
title: HtmlSaveOptions.CssStyleSheetType
second_title: Aspose.Words for .NET API 参考
description: HtmlSaveOptions 财产. 指定如何将 CSS层叠样式表样式导出为 HTMLMHTML 或 EPUB 默认值为Inline对于 HTML/MHTML 和 External对于 EPUB.
type: docs
weight: 60
url: /zh/net/aspose.words.saving/htmlsaveoptions/cssstylesheettype/
---
## HtmlSaveOptions.CssStyleSheetType property

指定如何将 CSS（层叠样式表）样式导出为 HTML、MHTML 或 EPUB。 默认值为Inline对于 HTML/MHTML 和 External对于 EPUB.

```csharp
public CssStyleSheetType CssStyleSheetType { get; set; }
```

### 评论

仅当保存为 HTML 时才支持将 CSS 样式表保存到外部文件中。 当您导出为其中一种容器格式（EPUB 或 MHTML）并指定 时External，CSS文件会被封装成 到输出包中。

### 例子

展示如何使用 HTML 转换创建的 CSS 样式表。

```csharp
public void ExternalCssFilenames()
{
    Document doc = new Document(MyDir + "Rendering.docx");

    // 创建一个“HtmlFixedSaveOptions”对象，我们可以将它传递给文档的“Save”方法
    // 修改我们如何将文档转换为 HTML。
    HtmlSaveOptions options = new HtmlSaveOptions();

    // 将“CssStylesheetType”属性设置为“CssStyleSheetType.External”以
    // 将保存的 HTML 文档与外部 CSS 样式表文件一起保存。
    options.CssStyleSheetType = CssStyleSheetType.External;

    // 下面是为输出 CSS 样式表指定目录和文件名的两种方法。
    // 1 - 使用“CssStyleSheetFileName”属性为我们的样式表分配一个文件名：
    options.CssStyleSheetFileName = ArtifactsDir + "SavingCallback.ExternalCssFilenames.css";

    // 2 - 使用自定义回调来命名我们的样式表：
    options.CssSavingCallback =
        new CustomCssSavingCallback(ArtifactsDir + "SavingCallback.ExternalCssFilenames.css", true, false);

    doc.Save(ArtifactsDir + "SavingCallback.ExternalCssFilenames.html", options);
}

/// <summary>
/// 设置自定义文件名以及外部 CSS 样式表的其他参数。
/// </summary>
private class CustomCssSavingCallback : ICssSavingCallback
{
    public CustomCssSavingCallback(string cssDocFilename, bool isExportNeeded, bool keepCssStreamOpen)
    {
        mCssTextFileName = cssDocFilename;
        mIsExportNeeded = isExportNeeded;
        mKeepCssStreamOpen = keepCssStreamOpen;
    }

    public void CssSaving(CssSavingArgs args)
    {
        // 我们可以通过“Document”属性访问整个源文档。
        Assert.True(args.Document.OriginalFileName.EndsWith("Rendering.docx"));

        args.CssStream = new FileStream(mCssTextFileName, FileMode.Create);
        args.IsExportNeeded = mIsExportNeeded;
        args.KeepCssStreamOpen = mKeepCssStreamOpen;

        Assert.True(args.CssStream.CanWrite);
    }

    private readonly string mCssTextFileName;
    private readonly bool mIsExportNeeded;
    private readonly bool mKeepCssStreamOpen;
}
```

### 也可以看看

* property [CssStyleSheetFileName](../cssstylesheetfilename/)
* enum [CssStyleSheetType](../../cssstylesheettype/)
* class [HtmlSaveOptions](../)
* 命名空间 [Aspose.Words.Saving](../../htmlsaveoptions/)
* 部件 [Aspose.Words](../../../)


