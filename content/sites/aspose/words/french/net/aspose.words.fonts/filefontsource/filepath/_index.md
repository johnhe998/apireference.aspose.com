---
title: FileFontSource.FilePath
second_title: Référence de l'API Aspose.Words pour .NET
description: FileFontSource propriété. Chemin daccès au fichier de police.
type: docs
weight: 30
url: /fr/net/aspose.words.fonts/filefontsource/filepath/
---
## FileFontSource.FilePath property

Chemin d'accès au fichier de police.

```csharp
public string FilePath { get; }
```

### Exemples

Montre comment utiliser un fichier de police dans le système de fichiers local comme source de police.

```csharp
FileFontSource fileFontSource = new FileFontSource(MyDir + "Alte DIN 1451 Mittelschrift.ttf", 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {fileFontSource});

Assert.AreEqual(MyDir + "Alte DIN 1451 Mittelschrift.ttf", fileFontSource.FilePath);
Assert.AreEqual(FontSourceType.FontFile, fileFontSource.Type);
Assert.AreEqual(0, fileFontSource.Priority);
```

### Voir également

* class [FileFontSource](../)
* espace de noms [Aspose.Words.Fonts](../../filefontsource/)
* Assemblée [Aspose.Words](../../../)


