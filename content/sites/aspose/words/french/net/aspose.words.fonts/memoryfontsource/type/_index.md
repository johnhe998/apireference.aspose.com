---
title: MemoryFontSource.Type
second_title: Référence de l'API Aspose.Words pour .NET
description: MemoryFontSource propriété. Renvoie le type de la source de la police.
type: docs
weight: 40
url: /fr/net/aspose.words.fonts/memoryfontsource/type/
---
## MemoryFontSource.Type property

Renvoie le type de la source de la police.

```csharp
public override FontSourceType Type { get; }
```

### Exemples

Montre comment utiliser un tableau d'octets avec les données d'un fichier de police comme source de police.

```csharp
byte[] fontBytes = File.ReadAllBytes(MyDir + "Alte DIN 1451 Mittelschrift.ttf");
MemoryFontSource memoryFontSource = new MemoryFontSource(fontBytes, 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {memoryFontSource});

Assert.AreEqual(FontSourceType.MemoryFont, memoryFontSource.Type);
Assert.AreEqual(0, memoryFontSource.Priority);
```

### Voir également

* enum [FontSourceType](../../fontsourcetype/)
* class [MemoryFontSource](../)
* espace de noms [Aspose.Words.Fonts](../../memoryfontsource/)
* Assemblée [Aspose.Words](../../../)


