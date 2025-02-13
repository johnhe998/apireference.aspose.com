---
title: StreamFontSource.OpenFontDataStream
second_title: Aspose.Words for .NET API 参考
description: StreamFontSource 方法. 此方法应按需打开带有字体数据的流
type: docs
weight: 30
url: /zh/net/aspose.words.fonts/streamfontsource/openfontdatastream/
---
## StreamFontSource.OpenFontDataStream method

此方法应按需打开带有字体数据的流。

```csharp
public abstract Stream OpenFontDataStream()
```

### 返回值

字体数据流。

### 评论

读取后将关闭流。无需显式关闭它。

### 例子

显示如何从流中加载字体。

```csharp
{
    FontSettings fontSettings = new FontSettings();
    fontSettings.SetFontsSources(new FontSourceBase[] {new StreamFontSourceFile()});

    DocumentBuilder builder = new DocumentBuilder();
    builder.Document.FontSettings = fontSettings;
    builder.Font.Name = "Kreon-Regular";
    builder.Writeln("Test aspose text when saving to PDF.");

    builder.Document.Save(ArtifactsDir + "FontSettings.StreamFontSourceFileRendering.pdf");
}

/// <summary>
/// 仅在需要时才加载字体数据，而不是将其存储在内存中
/// 对于“FontSettings”对象的整个生命周期。
/// </summary>
private class StreamFontSourceFile : StreamFontSource
{
    public override Stream OpenFontDataStream()
    {
        return File.OpenRead(FontsDir + "Kreon-Regular.ttf");
    }
}
```

### 也可以看看

* class [StreamFontSource](../)
* 命名空间 [Aspose.Words.Fonts](../../streamfontsource/)
* 部件 [Aspose.Words](../../../)


