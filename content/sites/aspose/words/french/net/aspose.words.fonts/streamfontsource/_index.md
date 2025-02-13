---
title: Class StreamFontSource
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Fonts.StreamFontSource classe. Classe de base pour la source de police de flux définie par lutilisateur.
type: docs
weight: 2860
url: /fr/net/aspose.words.fonts/streamfontsource/
---
## StreamFontSource class

Classe de base pour la source de police de flux définie par l'utilisateur.

```csharp
public abstract class StreamFontSource : FontSourceBase
```

## Propriétés

| Nom | La description |
| --- | --- |
| [CacheKey](../../aspose.words.fonts/streamfontsource/cachekey/) { get; } | La clé de cette source dans le cache. |
| [Priority](../../aspose.words.fonts/fontsourcebase/priority/) { get; } | Renvoie la priorité de la source de la police. |
| [Type](../../aspose.words.fonts/streamfontsource/type/) { get; } | Renvoie le type de la source de la police. |
| [WarningCallback](../../aspose.words.fonts/fontsourcebase/warningcallback/) { get; set; } | Appelé lors du traitement de la source de la police lorsqu'un problème est détecté pouvant entraîner une perte de fidélité de formatage. |

## Méthodes

| Nom | La description |
| --- | --- |
| [GetAvailableFonts](../../aspose.words.fonts/fontsourcebase/getavailablefonts/)() | Renvoie la liste des polices disponibles via cette source. |
| abstract [OpenFontDataStream](../../aspose.words.fonts/streamfontsource/openfontdatastream/)() | Cette méthode devrait ouvrir le flux avec les données de police à la demande. |

### Remarques

Pour utiliser la source de police de flux, vous devez créer une classe dérivée à partir de la`StreamFontSource` et fournir la mise en œuvre du[`OpenFontDataStream`](./openfontdatastream/) méthode.

[`OpenFontDataStream`](./openfontdatastream/)méthode peut être appelée plusieurs fois. Pour la première fois, il sera appelé lorsque Aspose.Words analysera les sources de polices fournies pour obtenir la liste des polices disponibles. Plus tard, il peut être appelé si la police est utilisée dans le document pour analyser les données de police et pour incorporer les données de police à certains formats de sortie.

`StreamFontSource` peut être utile car il permet de charger les données de la police uniquement lorsque cela est requis et de ne pas les stocker en mémoire pour le[`FontSettings`](../fontsettings/) durée de vie.

### Exemples

Montre comment charger des polices à partir du flux.

```csharp
{
    FontSettings fontSettings = new FontSettings();
    fontSettings.SetFontsSources(new FontSourceBase[] {new StreamFontSourceFile()});

    DocumentBuilder builder = new DocumentBuilder();
    builder.Document.FontSettings = fontSettings;
    builder.Font.Name = "Kreon-Regular";
    builder.Writeln("Test aspose text when saving to PDF.");

    builder.Document.Save(ArtifactsDir + "FontSettings.StreamFontSourceFileRendering.pdf");
}

/// <summary>
/// Charger les données de police uniquement lorsque cela est nécessaire au lieu de les stocker dans la mémoire
/// pour toute la durée de vie de l'objet "FontSettings".
/// </summary>
private class StreamFontSourceFile : StreamFontSource
{
    public override Stream OpenFontDataStream()
    {
        return File.OpenRead(FontsDir + "Kreon-Regular.ttf");
    }
}
```

### Voir également

* class [FontSourceBase](../fontsourcebase/)
* espace de noms [Aspose.Words.Fonts](../../aspose.words.fonts/)
* Assemblée [Aspose.Words](../../)


