---
title: Class DefaultFontSubstitutionRule
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Fonts.DefaultFontSubstitutionRule 班级. 默认字体替换规则
type: docs
weight: 2660
url: /zh/net/aspose.words.fonts/defaultfontsubstitutionrule/
---
## DefaultFontSubstitutionRule class

默认字体替换规则。

```csharp
public class DefaultFontSubstitutionRule : FontSubstitutionRule
```

## 特性

| 姓名 | 描述 |
| --- | --- |
| [DefaultFontName](../../aspose.words.fonts/defaultfontsubstitutionrule/defaultfontname/) { get; set; } | 获取或设置默认字体名称。 |
| virtual [Enabled](../../aspose.words.fonts/fontsubstitutionrule/enabled/) { get; set; } | 指定是否启用规则。 |

### 评论

如果原始字体不可用，此规则定义用于替换的单个默认字体名称。

### 例子

显示如何设置默认字体替换规则。

```csharp
Document doc = new Document();
FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;

// 获取 FontSettings 中的默认替换规则。
// 此规则会将所有缺失的字体替换为“Times New Roman”。
DefaultFontSubstitutionRule defaultFontSubstitutionRule =
    fontSettings.SubstitutionSettings.DefaultFontSubstitution;
Assert.True(defaultFontSubstitutionRule.Enabled);
Assert.AreEqual("Times New Roman", defaultFontSubstitutionRule.DefaultFontName);

// 将默认字体替换为“Courier New”。
defaultFontSubstitutionRule.DefaultFontName = "Courier New";

// 使用文档构建器，以我们不必看到替换发生的字体添加一些文本，
// 然后将结果呈现在 PDF 中。
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Missing Font";
builder.Writeln("Line written in a missing font, which will be substituted with Courier New.");

doc.Save(ArtifactsDir + "FontSettings.DefaultFontSubstitutionRule.pdf");
```

### 也可以看看

* class [FontSubstitutionRule](../fontsubstitutionrule/)
* 命名空间 [Aspose.Words.Fonts](../../aspose.words.fonts/)
* 部件 [Aspose.Words](../../)


