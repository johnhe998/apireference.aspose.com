---
title: Class FolderFontSource
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Fonts.FolderFontSource classe. Représente le dossier qui contient les fichiers de polices TrueType.
type: docs
weight: 2700
url: /fr/net/aspose.words.fonts/folderfontsource/
---
## FolderFontSource class

Représente le dossier qui contient les fichiers de polices TrueType.

```csharp
public class FolderFontSource : FontSourceBase
```

## Constructeurs

| Nom | La description |
| --- | --- |
| [FolderFontSource](folderfontsource/#constructor)(string, bool) | Ctor. |
| [FolderFontSource](folderfontsource/#constructor_1)(string, bool, int) | Ctor. |

## Propriétés

| Nom | La description |
| --- | --- |
| [FolderPath](../../aspose.words.fonts/folderfontsource/folderpath/) { get; } | Chemin d'accès au dossier. |
| [Priority](../../aspose.words.fonts/fontsourcebase/priority/) { get; } | Renvoie la priorité de la source de la police. |
| [ScanSubfolders](../../aspose.words.fonts/folderfontsource/scansubfolders/) { get; } | Détermine s'il faut analyser ou non les sous-dossiers. |
| override [Type](../../aspose.words.fonts/folderfontsource/type/) { get; } | Renvoie le type de la source de la police. |
| [WarningCallback](../../aspose.words.fonts/fontsourcebase/warningcallback/) { get; set; } | Appelé lors du traitement de la source de la police lorsqu'un problème est détecté pouvant entraîner une perte de fidélité de formatage. |

## Méthodes

| Nom | La description |
| --- | --- |
| [GetAvailableFonts](../../aspose.words.fonts/fontsourcebase/getavailablefonts/)() | Renvoie la liste des polices disponibles via cette source. |

### Exemples

Montre comment utiliser un dossier système local contenant des polices comme source de polices.

```csharp
// Crée une source de polices à partir d'un dossier contenant des fichiers de polices.
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, false, 1);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {folderFontSource});

Assert.AreEqual(FontsDir, folderFontSource.FolderPath);
Assert.AreEqual(false, folderFontSource.ScanSubfolders);
Assert.AreEqual(FontSourceType.FontsFolder, folderFontSource.Type);
Assert.AreEqual(1, folderFontSource.Priority);
```

### Voir également

* class [FontSourceBase](../fontsourcebase/)
* espace de noms [Aspose.Words.Fonts](../../aspose.words.fonts/)
* Assemblée [Aspose.Words](../../)


