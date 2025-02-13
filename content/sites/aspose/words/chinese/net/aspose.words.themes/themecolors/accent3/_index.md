---
title: ThemeColors.Accent3
second_title: Aspose.Words for .NET API 参考
description: ThemeColors 财产. 指定颜色口音 3.
type: docs
weight: 30
url: /zh/net/aspose.words.themes/themecolors/accent3/
---
## ThemeColors.Accent3 property

指定颜色口音 3.

```csharp
public Color Accent3 { get; set; }
```

### 例子

展示如何为主题设置自定义颜色和字体。

```csharp
Document doc = new Document(MyDir + "Theme colors.docx");

// “主题”对象让我们可以访问文档主题，这是默认字体和颜色的来源。
Theme theme = doc.Theme;

// 有些样式，比如“标题1”和“副标题”，会继承这些字体。
theme.MajorFonts.Latin = "Courier New";
theme.MinorFonts.Latin = "Agency FB";

// 其他语言在这个主题中也可能有他们的自定义字体。
Assert.AreEqual(string.Empty, theme.MajorFonts.ComplexScript);
Assert.AreEqual(string.Empty, theme.MajorFonts.EastAsian);
Assert.AreEqual(string.Empty, theme.MinorFonts.ComplexScript);
Assert.AreEqual(string.Empty, theme.MinorFonts.EastAsian);

//“颜色”属性包含来自 Microsoft Word 的调色板，
// 更改阴影或字体颜色时出现。
// 将自定义颜色应用到调色板，以便我们可以在 Microsoft Word 中轻松访问它们
// 例如，当我们通过“Home”更改字体颜色时 -> “字体”-> “字体颜色”，
// 或插入一个形状，然后通过“形状格式”为其设置颜色 -> “形状样式”。
ThemeColors colors = theme.Colors;
colors.Dark1 = Color.MidnightBlue;
colors.Light1 = Color.PaleGreen;
colors.Dark2 = Color.Indigo;
colors.Light2 = Color.Khaki;

colors.Accent1 = Color.OrangeRed;
colors.Accent2 = Color.LightSalmon;
colors.Accent3 = Color.Yellow;
colors.Accent4 = Color.Gold;
colors.Accent5 = Color.BlueViolet;
colors.Accent6 = Color.DarkViolet;

// 将自定义颜色应用于处于单击和未单击状态的超链接。
colors.Hyperlink = Color.Black;
colors.FollowedHyperlink = Color.Gray;

doc.Save(ArtifactsDir + "Themes.CustomColorsAndFonts.docx");
```

### 也可以看看

* class [ThemeColors](../)
* 命名空间 [Aspose.Words.Themes](../../themecolors/)
* 部件 [Aspose.Words](../../../)


