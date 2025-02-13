---
title: Class ThemeColors
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Themes.ThemeColors sınıf. On iki renk içeren belge temasının renk şemasını temsil eder.
type: docs
weight: 6180
url: /tr/net/aspose.words.themes/themecolors/
---
## ThemeColors class

On iki renk içeren belge temasının renk şemasını temsil eder.

ThemeColors nesnesi altı vurgu rengi, iki koyu renk, iki açık renk ve bir köprü ve takip edilen köprünün her biri için bir renk içerir.

```csharp
public class ThemeColors
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [Accent1](../../aspose.words.themes/themecolors/accent1/) { get; set; } | Rengi belirtir Vurgu 1. |
| [Accent2](../../aspose.words.themes/themecolors/accent2/) { get; set; } | Vurgu rengini belirtir 2. |
| [Accent3](../../aspose.words.themes/themecolors/accent3/) { get; set; } | Vurgu rengini belirtir 3. |
| [Accent4](../../aspose.words.themes/themecolors/accent4/) { get; set; } | Rengi belirtir Vurgu 4. |
| [Accent5](../../aspose.words.themes/themecolors/accent5/) { get; set; } | Rengi belirtir Vurgu 5. |
| [Accent6](../../aspose.words.themes/themecolors/accent6/) { get; set; } | Rengi belirtir Vurgu 6. |
| [Dark1](../../aspose.words.themes/themecolors/dark1/) { get; set; } | Rengi belirtir Koyu 1. |
| [Dark2](../../aspose.words.themes/themecolors/dark2/) { get; set; } | Koyu rengi belirtir 2. |
| [FollowedHyperlink](../../aspose.words.themes/themecolors/followedhyperlink/) { get; set; } | Tıklanan bir köprünün rengini belirtir. |
| [Hyperlink](../../aspose.words.themes/themecolors/hyperlink/) { get; set; } | Bir köprünün rengini belirtir. |
| [Light1](../../aspose.words.themes/themecolors/light1/) { get; set; } | Rengi belirtir Işık 1. |
| [Light2](../../aspose.words.themes/themecolors/light2/) { get; set; } | Açık 2. rengini belirtir |

### Örnekler

Temalar için özel renklerin ve yazı tiplerinin nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Theme colors.docx");

// "Tema" nesnesi, varsayılan yazı tiplerinin ve renklerin kaynağı olan belge temasına erişmemizi sağlar.
Theme theme = doc.Theme;

// "Heading 1" ve "Subtitle" gibi bazı stiller bu yazı tiplerini devralır.
theme.MajorFonts.Latin = "Courier New";
theme.MinorFonts.Latin = "Agency FB";

// Diğer diller de bu temada kendi özel yazı tiplerine sahip olabilir.
Assert.AreEqual(string.Empty, theme.MajorFonts.ComplexScript);
Assert.AreEqual(string.Empty, theme.MajorFonts.EastAsian);
Assert.AreEqual(string.Empty, theme.MinorFonts.ComplexScript);
Assert.AreEqual(string.Empty, theme.MinorFonts.EastAsian);

// "Renkler" özelliği, Microsoft Word'den renk paletini içerir,
// gölgelendirmeyi veya yazı tipi rengini değiştirirken görünen.
// Microsoft Word'de kolayca erişebilmemiz için renk paletine özel renkler uygulayın
// örneğin yazı tipi rengini "Ana Sayfa" ile değiştirdiğimizde -> "Yazı Tipi" -> "Yazı rengi",
// veya bir şekil ekleyin ve ardından "Şekil Formatı" ile bunun için bir renk ayarlayın -> "Şekil Stilleri".
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

// Tıklanan ve tıklanmayan durumlarındaki köprülere özel renkler uygulayın.
colors.Hyperlink = Color.Black;
colors.FollowedHyperlink = Color.Gray;

doc.Save(ArtifactsDir + "Themes.CustomColorsAndFonts.docx");
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Themes](../../aspose.words.themes/)
* toplantı [Aspose.Words](../../)


