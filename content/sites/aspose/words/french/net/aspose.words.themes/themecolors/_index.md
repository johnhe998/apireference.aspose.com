---
title: Class ThemeColors
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Themes.ThemeColors classe. Représente le jeu de couleurs du thème du document qui contient douze couleurs.
type: docs
weight: 6180
url: /fr/net/aspose.words.themes/themecolors/
---
## ThemeColors class

Représente le jeu de couleurs du thème du document qui contient douze couleurs.

L'objet ThemeColors contient six couleurs d'accentuation, deux couleurs sombres, deux couleurs claires et une couleur pour chacun des liens hypertexte et des liens hypertexte suivis.

```csharp
public class ThemeColors
```

## Propriétés

| Nom | La description |
| --- | --- |
| [Accent1](../../aspose.words.themes/themecolors/accent1/) { get; set; } | Spécifie la couleur Accent 1. |
| [Accent2](../../aspose.words.themes/themecolors/accent2/) { get; set; } | Spécifie la couleur Accent 2. |
| [Accent3](../../aspose.words.themes/themecolors/accent3/) { get; set; } | Spécifie la couleur Accent 3. |
| [Accent4](../../aspose.words.themes/themecolors/accent4/) { get; set; } | Spécifie la couleur Accent 4. |
| [Accent5](../../aspose.words.themes/themecolors/accent5/) { get; set; } | Spécifie la couleur Accent 5. |
| [Accent6](../../aspose.words.themes/themecolors/accent6/) { get; set; } | Spécifie la couleur Accent 6. |
| [Dark1](../../aspose.words.themes/themecolors/dark1/) { get; set; } | Spécifie la couleur Sombre 1. |
| [Dark2](../../aspose.words.themes/themecolors/dark2/) { get; set; } | Spécifie la couleur Sombre 2. |
| [FollowedHyperlink](../../aspose.words.themes/themecolors/followedhyperlink/) { get; set; } | Spécifie la couleur d'un lien hypertexte cliqué. |
| [Hyperlink](../../aspose.words.themes/themecolors/hyperlink/) { get; set; } | Spécifie la couleur d'un lien hypertexte. |
| [Light1](../../aspose.words.themes/themecolors/light1/) { get; set; } | Spécifie la couleur Lumière 1. |
| [Light2](../../aspose.words.themes/themecolors/light2/) { get; set; } | Spécifie la couleur Lumière 2. |

### Exemples

Montre comment définir des couleurs et des polices personnalisées pour les thèmes.

```csharp
Document doc = new Document(MyDir + "Theme colors.docx");

// L'objet "Theme" nous donne accès au thème du document, une source de polices et de couleurs par défaut.
Theme theme = doc.Theme;

// Certains styles, tels que "Titre 1" et "Sous-titre", hériteront de ces polices.
theme.MajorFonts.Latin = "Courier New";
theme.MinorFonts.Latin = "Agency FB";

// D'autres langues peuvent également avoir leurs polices personnalisées dans ce thème.
Assert.AreEqual(string.Empty, theme.MajorFonts.ComplexScript);
Assert.AreEqual(string.Empty, theme.MajorFonts.EastAsian);
Assert.AreEqual(string.Empty, theme.MinorFonts.ComplexScript);
Assert.AreEqual(string.Empty, theme.MinorFonts.EastAsian);

// La propriété "Colors" contient la palette de couleurs de Microsoft Word,
// qui apparaît lors du changement d'ombrage ou de couleur de police.
// Appliquez des couleurs personnalisées à la palette de couleurs afin de pouvoir y accéder facilement dans Microsoft Word
// lorsque nous changeons, par exemple, la couleur de la police via "Accueil" -> "Police" -> "Couleur de la police",
// ou insérez une forme, puis définissez une couleur pour celle-ci via "Format de forme" -> "Styles de forme".
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

// Appliquez des couleurs personnalisées aux hyperliens dans leurs états cliqués et non cliqués.
colors.Hyperlink = Color.Black;
colors.FollowedHyperlink = Color.Gray;

doc.Save(ArtifactsDir + "Themes.CustomColorsAndFonts.docx");
```

### Voir également

* espace de noms [Aspose.Words.Themes](../../aspose.words.themes/)
* Assemblée [Aspose.Words](../../)


