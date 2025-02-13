---
title: FontFallbackSettings.LoadMsOfficeFallbackSettings
second_title: Aspose.Words for .NET API 参考
description: FontFallbackSettings 方法. 加载模拟 Microsoft Word 后备并使用 Microsoft Office 字体的预定义后备设置
type: docs
weight: 30
url: /zh/net/aspose.words.fonts/fontfallbacksettings/loadmsofficefallbacksettings/
---
## FontFallbackSettings.LoadMsOfficeFallbackSettings method

加载模拟 Microsoft Word 后备并使用 Microsoft Office 字体的预定义后备设置。

```csharp
public void LoadMsOfficeFallbackSettings()
```

### 例子

显示如何加载预定义的后备字体设置。

```csharp
Document doc = new Document();

FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;
FontFallbackSettings fontFallbackSettings = fontSettings.FallbackSettings;

// 将默认的备用字体方案保存到 XML 文档。
// 例如，其中一个元素的 Range 值为“0C00-0C7F”，FallbackFonts 对应的值为“Vani”。
// 这意味着如果某些文本使用的字体没有 0x0C00-0x0C7F Unicode 块的符号，
// 后备方案将使用“Vani”字体替代品中的符号。
fontFallbackSettings.Save(ArtifactsDir + "FontSettings.FallbackSettings.Default.xml");

// 下面是我们可以选择的两种预定义的字体回退方案。
// 1 - 使用默认的 Microsoft Office 方案，与默认相同：
fontFallbackSettings.LoadMsOfficeFallbackSettings();
fontFallbackSettings.Save(ArtifactsDir + "FontSettings.FallbackSettings.LoadMsOfficeFallbackSettings.xml");

// 2 - 使用由 Google Noto 字体构建的方案：
fontFallbackSettings.LoadNotoFallbackSettings();
fontFallbackSettings.Save(ArtifactsDir + "FontSettings.FallbackSettings.LoadNotoFallbackSettings.xml");
```

### 也可以看看

* class [FontFallbackSettings](../)
* 命名空间 [Aspose.Words.Fonts](../../fontfallbacksettings/)
* 部件 [Aspose.Words](../../../)


