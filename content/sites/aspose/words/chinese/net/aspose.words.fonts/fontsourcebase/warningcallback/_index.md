---
title: FontSourceBase.WarningCallback
second_title: Aspose.Words for .NET API 参考
description: FontSourceBase 财产. 当检测到可能导致格式保真度丢失的问题时在处理字体源期间调用
type: docs
weight: 30
url: /zh/net/aspose.words.fonts/fontsourcebase/warningcallback/
---
## FontSourceBase.WarningCallback property

当检测到可能导致格式保真度丢失的问题时，在处理字体源期间调用。

```csharp
public IWarningCallback WarningCallback { get; set; }
```

### 例子

显示在使用字体源时如何调用警告回调。

```csharp
[Test]
public void FontSourceWarning()
{
    FontSettings settings = new FontSettings();
    settings.SetFontsFolder("bad folder?", false);

    FontSourceBase source = settings.GetFontsSources()[0];
    FontSourceWarningCollector callback = new FontSourceWarningCollector();
    source.WarningCallback = callback;

    // 获取要调用警告回调的字体列表。
    IList<PhysicalFontInfo> fontInfos = source.GetAvailableFonts();

    Assert.True(callback.FontSubstitutionWarnings[0].Description
        .Contains("Error loading font from the folder \"bad folder?\""));
}

private class FontSourceWarningCollector : IWarningCallback
{
    /// <summary>
    /// 在处理字体源时每次出现警告时调用。
    /// </summary>
    public void Warning(WarningInfo info)
    {
        FontSubstitutionWarnings.Warning(info);
    }

    public readonly WarningInfoCollection FontSubstitutionWarnings = new WarningInfoCollection();
}
```

### 也可以看看

* interface [IWarningCallback](../../../aspose.words/iwarningcallback/)
* class [FontSourceBase](../)
* 命名空间 [Aspose.Words.Fonts](../../fontsourcebase/)
* 部件 [Aspose.Words](../../../)


