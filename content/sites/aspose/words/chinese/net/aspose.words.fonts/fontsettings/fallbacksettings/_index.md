---
title: FontSettings.FallbackSettings
second_title: Aspose.Words for .NET API 参考
description: FontSettings 财产. 与字体回退机制相关的设置
type: docs
weight: 30
url: /zh/net/aspose.words.fonts/fontsettings/fallbacksettings/
---
## FontSettings.FallbackSettings property

与字体回退机制相关的设置。

```csharp
public FontFallbackSettings FallbackSettings { get; }
```

### 例子

展示如何在 Unicode 字符代码范围内分布备用字体。

```csharp
Document doc = new Document();

FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;
FontFallbackSettings fontFallbackSettings = fontSettings.FallbackSettings;

// 将我们的字体设置配置为仅从“MyFonts”文件夹中获取字体。
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, false);
fontSettings.SetFontsSources(new FontSourceBase[] {folderFontSource});

// 调用“BuildAutomatic”方法将生成一个备用方案
// 在尽可能多的 Unicode 字符代码中分配可访问的字体。
// 在我们的例子中，它只能访问“MyFonts”文件夹中的少数字体。
fontFallbackSettings.BuildAutomatic();
fontFallbackSettings.Save(ArtifactsDir + "FontSettings.FallbackSettingsCustom.BuildAutomatic.xml");

// 我们还可以从这样的文件中加载自定义替换方案。
// 此方案在“0000-00ff”Unicode 块中应用“AllegroOpen”字体，在“0100-024f”中应用“AllegroOpen”字体，
// 以及方案中其他字体未涵盖的所有其他范围内的“M+ 2m”字体。
fontFallbackSettings.Load(MyDir + "Custom font fallback settings.xml");

// 创建一个文档构建器并将其字体设置为我们的任何源中都不存在的字体。
// 我们的字体设置将为我们使用不可用字体键入的字符调用备用方案。
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Missing Font";

// 使用构建器打印从 0x0021 到 0x052F 的每个 Unicode 字符，
// 用描述行划分我们在自定义字体回退方案中定义的 Unicode 块。
for (int i = 0x0021; i < 0x0530; i++)
{
    switch (i)
    {
        case 0x0021:
            builder.Writeln(
                "\n\n0x0021 - 0x00FF: \nBasic Latin/Latin-1 Supplement Unicode blocks in \"AllegroOpen\" font:");
            break;
        case 0x0100:
            builder.Writeln(
                "\n\n0x0100 - 0x024F: \nLatin Extended A/B blocks, mostly in \"AllegroOpen\" font:");
            break;
        case 0x0250:
            builder.Writeln("\n\n0x0250 - 0x052F: \nIPA/Greek/Cyrillic blocks in \"M+ 2m\" font:");
            break;
    }

    builder.Write($"{Convert.ToChar(i)}");
}

doc.Save(ArtifactsDir + "FontSettings.FallbackSettingsCustom.pdf");
```

### 也可以看看

* class [FontFallbackSettings](../../fontfallbacksettings/)
* class [FontSettings](../)
* 命名空间 [Aspose.Words.Fonts](../../fontsettings/)
* 部件 [Aspose.Words](../../../)


