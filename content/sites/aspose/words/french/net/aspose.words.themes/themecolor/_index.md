---
title: Enum ThemeColor
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Themes.ThemeColor énumération. Spécifie les couleurs de thème pour les thèmes de document.
type: docs
weight: 6170
url: /fr/net/aspose.words.themes/themecolor/
---
## ThemeColor enumeration

Spécifie les couleurs de thème pour les thèmes de document.

```csharp
public enum ThemeColor
```

### Valeurs

| Nom | Évaluer | La description |
| --- | --- | --- |
| None | `-1` | Aucune couleur. |
| Dark1 | `0` | Couleur principale sombre 1. |
| Light1 | `1` | Couleur principale claire 1. |
| Dark2 | `2` | Couleur principale sombre 2. |
| Light2 | `3` | Couleur principale claire 2. |
| Accent1 | `4` | Couleur d'accent 1. |
| Accent2 | `5` | Couleur d'accent 2. |
| Accent3 | `6` | Couleur d'accent 3. |
| Accent4 | `7` | Couleur d'accentuation 4. |
| Accent5 | `8` | Couleur d'accent 5. |
| Accent6 | `9` | Couleur d'accent 6. |
| Hyperlink | `10` | Couleur du lien hypertexte. |
| FollowedHyperlink | `11` | Couleur du lien hypertexte suivi. |
| Text1 | `12` | Couleur du texte 1. |
| Text2 | `13` | Couleur du texte 2. |
| Background1 | `14` | Couleur de fond 1. |
| Background2 | `15` | Couleur de fond 2. |

### Remarques

La couleur de thème spécifiée est une référence à l'une des couleurs de thème prédéfinies, située dans la partie Thème du document , qui permet de définir les informations de couleur de manière centralisée dans le document.

### Exemples

Montre comment créer et utiliser un style thématique.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln();

// Crée un style avec les propriétés de police du thème.
Style style = doc.Styles.Add(StyleType.Paragraph, "ThemedStyle");
style.Font.ThemeFont = ThemeFont.Major;
style.Font.ThemeColor = ThemeColor.Accent5;
style.Font.TintAndShade = 0.3;

builder.ParagraphFormat.StyleName = "ThemedStyle";
builder.Writeln("Text with themed style");
```

Montre comment travailler avec les polices et les couleurs de thème.

```csharp
Document doc = new Document();

// Définit les polices pour les langues utilisées par défaut.
doc.Theme.MinorFonts.Latin = "Algerian";
doc.Theme.MinorFonts.EastAsian = "Aharoni";
doc.Theme.MinorFonts.ComplexScript = "Andalus";

Font font = doc.Styles["Normal"].Font;
Console.WriteLine("Originally the Normal style theme color is: {0} and RGB color is: {1}\n", font.ThemeColor, font.Color);

// Nous pouvons utiliser la police et la couleur du thème au lieu des valeurs par défaut.
font.ThemeFont = ThemeFont.Minor;
font.ThemeColor = ThemeColor.Accent2;

Assert.AreEqual(ThemeFont.Minor, font.ThemeFont);
Assert.AreEqual("Algerian", font.Name);

Assert.AreEqual(ThemeFont.Minor, font.ThemeFontAscii);
Assert.AreEqual("Algerian", font.NameAscii);

Assert.AreEqual(ThemeFont.Minor, font.ThemeFontBi);
Assert.AreEqual("Andalus", font.NameBi);

Assert.AreEqual(ThemeFont.Minor, font.ThemeFontFarEast);
Assert.AreEqual("Aharoni", font.NameFarEast);

Assert.AreEqual(ThemeFont.Minor, font.ThemeFontOther);
Assert.AreEqual("Algerian", font.NameOther);

Assert.AreEqual(ThemeColor.Accent2, font.ThemeColor);
Assert.AreEqual(Color.Empty, font.Color);

// Il existe plusieurs façons de réinitialiser leur police et leur couleur.
// 1 - En définissant ThemeFont.None/ThemeColor.None :
font.ThemeFont = ThemeFont.None;
font.ThemeColor = ThemeColor.None;

Assert.AreEqual(ThemeFont.None, font.ThemeFont);
Assert.AreEqual("Algerian", font.Name);

Assert.AreEqual(ThemeFont.None, font.ThemeFontAscii);
Assert.AreEqual("Algerian", font.NameAscii);

Assert.AreEqual(ThemeFont.None, font.ThemeFontBi);
Assert.AreEqual("Andalus", font.NameBi);

Assert.AreEqual(ThemeFont.None, font.ThemeFontFarEast);
Assert.AreEqual("Aharoni", font.NameFarEast);

Assert.AreEqual(ThemeFont.None, font.ThemeFontOther);
Assert.AreEqual("Algerian", font.NameOther);

Assert.AreEqual(ThemeColor.None, font.ThemeColor);
Assert.AreEqual(Color.Empty, font.Color);

// 2 - En définissant des noms de polices/couleurs non thématiques :
font.Name = "Arial";
font.Color = Color.Blue;

Assert.AreEqual(ThemeFont.None, font.ThemeFont);
Assert.AreEqual("Arial", font.Name);

Assert.AreEqual(ThemeFont.None, font.ThemeFontAscii);
Assert.AreEqual("Arial", font.NameAscii);

Assert.AreEqual(ThemeFont.None, font.ThemeFontBi);
Assert.AreEqual("Arial", font.NameBi);

Assert.AreEqual(ThemeFont.None, font.ThemeFontFarEast);
Assert.AreEqual("Arial", font.NameFarEast);

Assert.AreEqual(ThemeFont.None, font.ThemeFontOther);
Assert.AreEqual("Arial", font.NameOther);

Assert.AreEqual(ThemeColor.None, font.ThemeColor);
Assert.AreEqual(Color.Blue.ToArgb(), font.Color.ToArgb());
```

### Voir également

* espace de noms [Aspose.Words.Themes](../../aspose.words.themes/)
* Assemblée [Aspose.Words](../../)


