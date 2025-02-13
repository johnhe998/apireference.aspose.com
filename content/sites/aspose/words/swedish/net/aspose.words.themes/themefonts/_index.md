---
title: Class ThemeFonts
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Themes.ThemeFonts klass. Representerar en samling teckensnitt i teckensnittsschemat vilket gör det möjligt att ange olika teckensnitt för olika språkLatin EastAsian ochComplexScript .
type: docs
weight: 6200
url: /sv/net/aspose.words.themes/themefonts/
---
## ThemeFonts class

Representerar en samling teckensnitt i teckensnittsschemat, vilket gör det möjligt att ange olika teckensnitt för olika språk[`Latin`](./latin/) ,[`EastAsian`](./eastasian/) och[`ComplexScript`](./complexscript/) .

```csharp
public class ThemeFonts
```

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [ComplexScript](../../aspose.words.themes/themefonts/complexscript/) { get; set; } | Anger teckensnittsnamn för ComplexScript-tecken. |
| [EastAsian](../../aspose.words.themes/themefonts/eastasian/) { get; set; } | Anger teckensnittsnamn för östasiatiska tecken. |
| [Latin](../../aspose.words.themes/themefonts/latin/) { get; set; } | Anger teckensnittsnamn för latinska tecken. |

### Exempel

Visar hur du ställer in anpassade färger och teckensnitt för teman.

```csharp
Document doc = new Document(MyDir + "Theme colors.docx");

// "Theme"-objektet ger oss tillgång till dokumenttemat, en källa till standardteckensnitt och färger.
Theme theme = doc.Theme;

// Vissa stilar, som "Rubrik 1" och "Underrubrik", kommer att ärva dessa typsnitt.
theme.MajorFonts.Latin = "Courier New";
theme.MinorFonts.Latin = "Agency FB";

// Andra språk kan också ha sina anpassade typsnitt i detta tema.
Assert.AreEqual(string.Empty, theme.MajorFonts.ComplexScript);
Assert.AreEqual(string.Empty, theme.MajorFonts.EastAsian);
Assert.AreEqual(string.Empty, theme.MinorFonts.ComplexScript);
Assert.AreEqual(string.Empty, theme.MinorFonts.EastAsian);

// Egenskapen "Colors" innehåller färgpaletten från Microsoft Word,
// som visas när du ändrar skuggning eller teckensnittsfärg.
// Använd anpassade färger på färgpaletten så att vi har enkel tillgång till dem i Microsoft Word
// när vi till exempel ändrar teckensnittsfärg via "Hem" -> "Teckensnitt" -> "Fontfärg",
// eller infoga en form och ställ sedan in en färg för den via "Shape Format" -> "Formstilar".
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

// Tillämpa anpassade färger på hyperlänkar i deras klickade och oklickade tillstånd.
colors.Hyperlink = Color.Black;
colors.FollowedHyperlink = Color.Gray;

doc.Save(ArtifactsDir + "Themes.CustomColorsAndFonts.docx");
```

### Se även

* namnutrymme [Aspose.Words.Themes](../../aspose.words.themes/)
* hopsättning [Aspose.Words](../../)


