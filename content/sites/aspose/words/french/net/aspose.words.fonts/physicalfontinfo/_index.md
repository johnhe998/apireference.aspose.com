---
title: Class PhysicalFontInfo
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Fonts.PhysicalFontInfo classe. Spécifie des informations sur la police physique disponible pour le moteur de polices Aspose.Words.
type: docs
weight: 2850
url: /fr/net/aspose.words.fonts/physicalfontinfo/
---
## PhysicalFontInfo class

Spécifie des informations sur la police physique disponible pour le moteur de polices Aspose.Words.

```csharp
public class PhysicalFontInfo
```

## Propriétés

| Nom | La description |
| --- | --- |
| [FilePath](../../aspose.words.fonts/physicalfontinfo/filepath/) { get; } | Chemin d'accès au fichier de police, le cas échéant. |
| [FontFamilyName](../../aspose.words.fonts/physicalfontinfo/fontfamilyname/) { get; } | Nom de famille de la police. |
| [FullFontName](../../aspose.words.fonts/physicalfontinfo/fullfontname/) { get; } | Nom complet de la police. |
| [Version](../../aspose.words.fonts/physicalfontinfo/version/) { get; } | Chaîne de version de la police. |

### Exemples

Montre comment répertorier les polices disponibles.

```csharp
// Configurez Aspose.Words pour sourcer les polices à partir d'un dossier personnalisé, puis imprimez toutes les polices disponibles.
FontSourceBase[] folderFontSource = { new FolderFontSource(FontsDir, true) };

foreach (PhysicalFontInfo fontInfo in folderFontSource[0].GetAvailableFonts())
{
    Console.WriteLine("FontFamilyName : {0}", fontInfo.FontFamilyName);
    Console.WriteLine("FullFontName  : {0}", fontInfo.FullFontName);
    Console.WriteLine("Version  : {0}", fontInfo.Version);
    Console.WriteLine("FilePath : {0}\n", fontInfo.FilePath);
}
```

### Voir également

* espace de noms [Aspose.Words.Fonts](../../aspose.words.fonts/)
* Assemblée [Aspose.Words](../../)


