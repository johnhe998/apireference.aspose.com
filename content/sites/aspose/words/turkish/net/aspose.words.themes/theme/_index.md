---
title: Class Theme
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Themes.Theme sınıf. Belge Temasını temsil eder ve aşağıdakiler dahil ana tema bölümlerine erişim sağlarMajorFonts MinorFonts veColors
type: docs
weight: 6160
url: /tr/net/aspose.words.themes/theme/
---
## Theme class

Belge Temasını temsil eder ve aşağıdakiler dahil ana tema bölümlerine erişim sağlar:[`MajorFonts`](./majorfonts/) ,[`MinorFonts`](./minorfonts/) ve[`Colors`](./colors/)

```csharp
public class Theme
```

## yapıcılar

| İsim | Tanım |
| --- | --- |
| [Theme](theme/)() | Default_Constructor |

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [Colors](../../aspose.words.themes/theme/colors/) { get; } | Belge için tema renkleri kümesini belirlemeye izin verir. |
| [MajorFonts](../../aspose.words.themes/theme/majorfonts/) { get; } | Farklı diller için ana yazı tiplerini belirlemeye izin verir. |
| [MinorFonts](../../aspose.words.themes/theme/minorfonts/) { get; } | Farklı diller için küçük yazı tiplerini belirlemeye izin verir. |

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


