---
title: FontFallbackSettings.LoadMsOfficeFallbackSettings
second_title: Référence de l'API Aspose.Words pour .NET
description: FontFallbackSettings méthode. Charge les paramètres de secours prédéfinis qui imitent le secours de Microsoft Word et utilisent les polices Microsoft Office.
type: docs
weight: 30
url: /fr/net/aspose.words.fonts/fontfallbacksettings/loadmsofficefallbacksettings/
---
## FontFallbackSettings.LoadMsOfficeFallbackSettings method

Charge les paramètres de secours prédéfinis qui imitent le secours de Microsoft Word et utilisent les polices Microsoft Office.

```csharp
public void LoadMsOfficeFallbackSettings()
```

### Exemples

Montre comment charger les paramètres de police de secours prédéfinis.

```csharp
Document doc = new Document();

FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;
FontFallbackSettings fontFallbackSettings = fontSettings.FallbackSettings;

// Enregistre le jeu de polices de secours par défaut dans un document XML.
// Par exemple, l'un des éléments a une valeur de "0C00-0C7F" pour Range et une valeur "Vani" correspondante pour FallbackFonts.
// Cela signifie que si la police utilisée par certains textes n'a pas de symboles pour le bloc Unicode 0x0C00-0x0C7F,
// le schéma de secours utilisera les symboles du substitut de police "Vani".
fontFallbackSettings.Save(ArtifactsDir + "FontSettings.FallbackSettings.Default.xml");

// Vous trouverez ci-dessous deux schémas de remplacement de polices prédéfinis parmi lesquels nous pouvons choisir.
// 1 - Utilisez le schéma Microsoft Office par défaut, qui est le même que celui par défaut :
fontFallbackSettings.LoadMsOfficeFallbackSettings();
fontFallbackSettings.Save(ArtifactsDir + "FontSettings.FallbackSettings.LoadMsOfficeFallbackSettings.xml");

// 2 - Utilisez le schéma construit à partir des polices Google Noto :
fontFallbackSettings.LoadNotoFallbackSettings();
fontFallbackSettings.Save(ArtifactsDir + "FontSettings.FallbackSettings.LoadNotoFallbackSettings.xml");
```

### Voir également

* class [FontFallbackSettings](../)
* espace de noms [Aspose.Words.Fonts](../../fontfallbacksettings/)
* Assemblée [Aspose.Words](../../../)


