---
title: FileFontSource.Type
second_title: Aspose.Words per .NET API Reference
description: FileFontSource proprietà. Restituisce il tipo di origine del carattere.
type: docs
weight: 40
url: /it/net/aspose.words.fonts/filefontsource/type/
---
## FileFontSource.Type property

Restituisce il tipo di origine del carattere.

```csharp
public override FontSourceType Type { get; }
```

### Esempi

Mostra come utilizzare un file di font nel file system locale come origine di font.

```csharp
FileFontSource fileFontSource = new FileFontSource(MyDir + "Alte DIN 1451 Mittelschrift.ttf", 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {fileFontSource});

Assert.AreEqual(MyDir + "Alte DIN 1451 Mittelschrift.ttf", fileFontSource.FilePath);
Assert.AreEqual(FontSourceType.FontFile, fileFontSource.Type);
Assert.AreEqual(0, fileFontSource.Priority);
```

### Guarda anche

* enum [FontSourceType](../../fontsourcetype/)
* class [FileFontSource](../)
* spazio dei nomi [Aspose.Words.Fonts](../../filefontsource/)
* assemblea [Aspose.Words](../../../)


