---
title: Class FileFormatUtil
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.FileFormatUtil classe. Fournit des méthodes utilitaires pour travailler avec les formats de fichier telles que la détection du format de fichier ou la conversion des extensions de fichier vers/depuis les énumérations de format de fichier.
type: docs
weight: 2640
url: /fr/net/aspose.words/fileformatutil/
---
## FileFormatUtil class

Fournit des méthodes utilitaires pour travailler avec les formats de fichier, telles que la détection du format de fichier ou la conversion des extensions de fichier vers/depuis les énumérations de format de fichier.

```csharp
public static class FileFormatUtil
```

## Méthodes

| Nom | La description |
| --- | --- |
| static [ContentTypeToLoadFormat](../../aspose.words/fileformatutil/contenttypetoloadformat/)(string) | Convertit le type de contenu IANA en une valeur énumérée de format de chargement. |
| static [ContentTypeToSaveFormat](../../aspose.words/fileformatutil/contenttypetosaveformat/)(string) | Convertit le type de contenu IANA en une valeur énumérée de format de sauvegarde. |
| static [DetectFileFormat](../../aspose.words/fileformatutil/detectfileformat/#detectfileformat)(Stream) | Détecte et renvoie les informations sur un format d'un document stocké dans un flux. |
| static [DetectFileFormat](../../aspose.words/fileformatutil/detectfileformat/#detectfileformat_1)(string) | Détecte et renvoie les informations sur un format d'un document stocké dans un fichier disque. |
| static [ExtensionToSaveFormat](../../aspose.words/fileformatutil/extensiontosaveformat/)(string) | Convertit une extension de nom de fichier en un[`SaveFormat`](../saveformat/) valeur. |
| static [ImageTypeToExtension](../../aspose.words/fileformatutil/imagetypetoextension/)(ImageType) | Convertit une valeur énumérée de type d'image Aspose.Words en une extension de fichier. L'extension renvoyée est une chaîne en minuscules précédée d'un point. |
| static [LoadFormatToExtension](../../aspose.words/fileformatutil/loadformattoextension/)(LoadFormat) | Convertit une valeur énumérée au format de chargement en une extension de fichier. L'extension renvoyée est une chaîne en minuscules précédée d'un point. |
| static [LoadFormatToSaveFormat](../../aspose.words/fileformatutil/loadformattosaveformat/)(LoadFormat) | Convertit un[`LoadFormat`](../loadformat/) valeur à un[`SaveFormat`](../saveformat/) valeur si possible. |
| static [SaveFormatToExtension](../../aspose.words/fileformatutil/saveformattoextension/)(SaveFormat) | Convertit une valeur énumérée au format de sauvegarde en une extension de fichier. L'extension renvoyée est une chaîne en minuscules précédée d'un point. |
| static [SaveFormatToLoadFormat](../../aspose.words/fileformatutil/saveformattoloadformat/)(SaveFormat) | Convertit un[`SaveFormat`](../saveformat/) valeur à un[`LoadFormat`](../loadformat/) valeur si possible. |

### Exemples

Montre comment détecter l'encodage dans un fichier html.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(MyDir + "Document.html");

Assert.AreEqual(LoadFormat.Html, info.LoadFormat);

// La propriété Encoding est utilisée uniquement lorsque nous créons un objet FileFormatInfo pour un document html.
Assert.AreEqual("Western European (Windows)", info.Encoding.EncodingName);
Assert.AreEqual(1252, info.Encoding.CodePage);
```

### Voir également

* espace de noms [Aspose.Words](../../aspose.words/)
* Assemblée [Aspose.Words](../../)


