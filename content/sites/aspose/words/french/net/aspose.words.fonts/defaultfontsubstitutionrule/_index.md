---
title: Class DefaultFontSubstitutionRule
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Fonts.DefaultFontSubstitutionRule classe. Règle de substitution de police par défaut.
type: docs
weight: 2660
url: /fr/net/aspose.words.fonts/defaultfontsubstitutionrule/
---
## DefaultFontSubstitutionRule class

Règle de substitution de police par défaut.

```csharp
public class DefaultFontSubstitutionRule : FontSubstitutionRule
```

## Propriétés

| Nom | La description |
| --- | --- |
| [DefaultFontName](../../aspose.words.fonts/defaultfontsubstitutionrule/defaultfontname/) { get; set; } | Obtient ou définit le nom de la police par défaut. |
| virtual [Enabled](../../aspose.words.fonts/fontsubstitutionrule/enabled/) { get; set; } | Spécifie si la règle est activée ou non. |

### Remarques

Cette règle définit un seul nom de police par défaut à utiliser pour la substitution si la police d'origine n'est pas disponible.

### Exemples

Montre comment définir la règle de substitution de police par défaut.

```csharp
Document doc = new Document();
FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;

// Récupère la règle de substitution par défaut dans FontSettings.
// Cette règle remplacera toutes les polices manquantes par "Times New Roman".
DefaultFontSubstitutionRule defaultFontSubstitutionRule =
    fontSettings.SubstitutionSettings.DefaultFontSubstitution;
Assert.True(defaultFontSubstitutionRule.Enabled);
Assert.AreEqual("Times New Roman", defaultFontSubstitutionRule.DefaultFontName);

// Définit le substitut de police par défaut sur "Courier New".
defaultFontSubstitutionRule.DefaultFontName = "Courier New";

// A l'aide d'un constructeur de document, ajoutez du texte dans une police dont nous n'avons pas besoin pour voir la substitution se produire,
// puis affichez le résultat dans un PDF.
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Missing Font";
builder.Writeln("Line written in a missing font, which will be substituted with Courier New.");

doc.Save(ArtifactsDir + "FontSettings.DefaultFontSubstitutionRule.pdf");
```

### Voir également

* class [FontSubstitutionRule](../fontsubstitutionrule/)
* espace de noms [Aspose.Words.Fonts](../../aspose.words.fonts/)
* Assemblée [Aspose.Words](../../)


