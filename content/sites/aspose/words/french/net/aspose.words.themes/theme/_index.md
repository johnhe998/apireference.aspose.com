---
title: Class Theme
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Themes.Theme classe. Représente le thème du document et donne accès aux principales parties du thème y comprisMajorFonts MinorFonts etColors
type: docs
weight: 6160
url: /fr/net/aspose.words.themes/theme/
---
## Theme class

Représente le thème du document et donne accès aux principales parties du thème, y compris[`MajorFonts`](./majorfonts/) ,[`MinorFonts`](./minorfonts/) et[`Colors`](./colors/)

```csharp
public class Theme
```

## Constructeurs

| Nom | La description |
| --- | --- |
| [Theme](theme/)() | Default_Constructor |

## Propriétés

| Nom | La description |
| --- | --- |
| [Colors](../../aspose.words.themes/theme/colors/) { get; } | Permet de spécifier le jeu de couleurs de thème pour le document. |
| [MajorFonts](../../aspose.words.themes/theme/majorfonts/) { get; } | Permet de spécifier le jeu de polices principales pour différentes langues. |
| [MinorFonts](../../aspose.words.themes/theme/minorfonts/) { get; } | Permet de spécifier le jeu de polices mineures pour différentes langues. |

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


