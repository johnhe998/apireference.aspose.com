---
title: FontSavingArgs.OriginalFileName
second_title: Aspose.Words for .NET API 参考
description: FontSavingArgs 财产. 获取带有扩展名的原始字体文件名
type: docs
weight: 100
url: /zh/net/aspose.words.saving/fontsavingargs/originalfilename/
---
## FontSavingArgs.OriginalFileName property

获取带有扩展名的原始字体文件名。

```csharp
public string OriginalFileName { get; }
```

### 评论

此属性包含当前字体的原始文件名（如果已知）。否则它可以是一个空字符串。

### 例子

展示如何定义自定义逻辑以在保存为 HTML 时导出字体。

```csharp
{
    Document doc = new Document(MyDir + "Rendering.docx");

    // 配置 SaveOptions 对象以将字体导出到单独的文件。
    // 设置一个以自定义方式处理字体保存的回调。
    HtmlSaveOptions options = new HtmlSaveOptions
    {
        ExportFontResources = true,
        FontSavingCallback = new HandleFontSaving()
    };

    // 回调将导出 .ttf 文件并将它们与输出文档一起保存。
    doc.Save(ArtifactsDir + "HtmlSaveOptions.SaveExportedFonts.html", options);

    foreach (string fontFilename in Array.FindAll(Directory.GetFiles(ArtifactsDir), s => s.EndsWith(".ttf")))
    {
        Console.WriteLine(fontFilename);
    }

/// <summary>
/// 打印有关导出字体的信息并将它们保存在与其输出 .html 相同的本地系统文件夹中。
/// </summary>
public class HandleFontSaving : IFontSavingCallback
{
    void IFontSavingCallback.FontSaving(FontSavingArgs args)
    {
        Console.Write($"Font:\t{args.FontFamilyName}");
        if (args.Bold) Console.Write(", bold");
        if (args.Italic) Console.Write(", italic");
        Console.WriteLine($"\nSource:\t{args.OriginalFileName}, {args.OriginalFileSize} bytes\n");

        // 我们也可以从这里访问源文档。
        Assert.True(args.Document.OriginalFileName.EndsWith("Rendering.docx"));

        Assert.True(args.IsExportNeeded);
        Assert.True(args.IsSubsettingNeeded);

        // 有两种保存导出字体的方法。
        // 1 - 将其保存到本地文件系统位置：
        args.FontFileName = args.OriginalFileName.Split(Path.DirectorySeparatorChar).Last();

        // 2 - 将其保存到流中：
        args.FontStream =
            new FileStream(ArtifactsDir + args.OriginalFileName.Split(Path.DirectorySeparatorChar).Last(), FileMode.Create);
        Assert.False(args.KeepFontStreamOpen);
    }
}
```

### 也可以看看

* class [FontSavingArgs](../)
* 命名空间 [Aspose.Words.Saving](../../fontsavingargs/)
* 部件 [Aspose.Words](../../../)


