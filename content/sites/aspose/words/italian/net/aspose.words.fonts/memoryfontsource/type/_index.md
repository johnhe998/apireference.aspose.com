---
title: MemoryFontSource.Type
second_title: Aspose.Words per .NET API Reference
description: MemoryFontSource proprietà. Restituisce il tipo di origine del carattere.
type: docs
weight: 40
url: /it/net/aspose.words.fonts/memoryfontsource/type/
---
## MemoryFontSource.Type property

Restituisce il tipo di origine del carattere.

```csharp
public override FontSourceType Type { get; }
```

### Esempi

Mostra come utilizzare una matrice di byte con i dati di un file di font come origine di font.

```csharp
byte[] fontBytes = File.ReadAllBytes(MyDir + "Alte DIN 1451 Mittelschrift.ttf");
MemoryFontSource memoryFontSource = new MemoryFontSource(fontBytes, 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {memoryFontSource});

Assert.AreEqual(FontSourceType.MemoryFont, memoryFontSource.Type);
Assert.AreEqual(0, memoryFontSource.Priority);
```

### Guarda anche

* enum [FontSourceType](../../fontsourcetype/)
* class [MemoryFontSource](../)
* spazio dei nomi [Aspose.Words.Fonts](../../memoryfontsource/)
* assemblea [Aspose.Words](../../../)


