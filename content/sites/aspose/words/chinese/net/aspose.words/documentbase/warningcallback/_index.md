---
title: DocumentBase.WarningCallback
second_title: Aspose.Words for .NET API 参考
description: DocumentBase 财产. 当检测到可能导致数据中出现 或格式保真度丢失的问题时在各种文档处理过程中调用
type: docs
weight: 90
url: /zh/net/aspose.words/documentbase/warningcallback/
---
## DocumentBase.WarningCallback property

当检测到可能导致数据中出现 或格式保真度丢失的问题时，在各种文档处理过程中调用。

```csharp
public IWarningCallback WarningCallback { get; set; }
```

### 评论

文档可能在其存在的任何阶段产生警告，因此尽早设置警告回调 as 以避免警告丢失非常重要。例如这样的属性[`PageCount`](../../document/pagecount/) 实际构建文档布局，稍后用于渲染，如果 警告回调仅用于稍后的渲染调用，布局警告可能会丢失。

### 例子

展示如何使用 IWarningCallback 接口来监控字体替换警告。

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Font.Name = "Times New Roman";
    builder.Writeln("Hello world!");

    FontSubstitutionWarningCollector callback = new FontSubstitutionWarningCollector();
    doc.WarningCallback = callback;

    // 存储当前字体源集合，这将是每个文档的默认字体源
    // 我们没有指定不同的字体源。
    FontSourceBase[] originalFontSources = FontSettings.DefaultInstance.GetFontsSources();

    // 出于测试目的，我们将 Aspose.Words 设置为仅在不存在的文件夹中查找字体。
    FontSettings.DefaultInstance.SetFontsFolder(string.Empty, false);

    // 渲染文档时，会找不到“Times New Roman”字体的地方。
    // 这将导致字体替换警告，我们的回调将检测到该警告。
    doc.Save(ArtifactsDir + "FontSettings.SubstitutionWarning.pdf");

    FontSettings.DefaultInstance.SetFontsSources(originalFontSources);

    Assert.True(callback.FontSubstitutionWarnings[0].Description
        .Equals(
            "Font 'Times New Roman' has not been found. Using 'Fanwood' font instead. Reason: first available font."));
}

private class FontSubstitutionWarningCollector : IWarningCallback
{
    /// <summary>
    /// 在加载/保存过程中每次出现警告时调用。
    /// </summary>
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.FontSubstitution)
            FontSubstitutionWarnings.Warning(info);
    }

    public WarningInfoCollection FontSubstitutionWarnings = new WarningInfoCollection();
}
```

演示如何设置属性以从可用字体源中查找缺失字体的最接近匹配项。

```csharp
[Test]
public void EnableFontSubstitution()
{
    // 打开一个文档，其中包含使用我们的任何字体源中都不存在的字体格式化的文本。
    Document doc = new Document(MyDir + "Missing font.docx");

    // 分配一个回调来处理字体替换警告。
    HandleDocumentSubstitutionWarnings substitutionWarningHandler = new HandleDocumentSubstitutionWarnings();
    doc.WarningCallback = substitutionWarningHandler;

    // 设置默认字体名称并启用字体替换。
    FontSettings fontSettings = new FontSettings();
    fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
    ;
    fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = true;

    // 如果我们保存缺少字体的文档，我们将收到字体替换警告。
    doc.FontSettings = fontSettings;
    doc.Save(ArtifactsDir + "FontSettings.EnableFontSubstitution.pdf");

    using (IEnumerator<WarningInfo> warnings = substitutionWarningHandler.FontWarnings.GetEnumerator())
        while (warnings.MoveNext())
            Console.WriteLine(warnings.Current.Description);

    // 我们还可以验证集合中的警告并清除它们。
    Assert.AreEqual(WarningSource.Layout, substitutionWarningHandler.FontWarnings[0].Source);
    Assert.AreEqual(
        "Font '28 Days Later' has not been found. Using 'Calibri' font instead. Reason: alternative name from document.",
        substitutionWarningHandler.FontWarnings[0].Description);

    substitutionWarningHandler.FontWarnings.Clear();

    Assert.That(substitutionWarningHandler.FontWarnings, Is.Empty);
}

public class HandleDocumentSubstitutionWarnings : IWarningCallback
{
    /// <summary>
    /// 在加载/保存过程中每次出现警告时调用。
    /// </summary>
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.FontSubstitution)
            FontWarnings.Warning(info);
    }

    public WarningInfoCollection FontWarnings = new WarningInfoCollection();
}
```

### 也可以看看

* interface [IWarningCallback](../../iwarningcallback/)
* class [DocumentBase](../)
* 命名空间 [Aspose.Words](../../documentbase/)
* 部件 [Aspose.Words](../../../)


