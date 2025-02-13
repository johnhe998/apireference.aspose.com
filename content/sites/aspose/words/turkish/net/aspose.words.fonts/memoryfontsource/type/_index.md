---
title: MemoryFontSource.Type
second_title: Aspose.Words for .NET API Referansı
description: MemoryFontSource mülk. Yazı tipi kaynağının türünü döndürür.
type: docs
weight: 40
url: /tr/net/aspose.words.fonts/memoryfontsource/type/
---
## MemoryFontSource.Type property

Yazı tipi kaynağının türünü döndürür.

```csharp
public override FontSourceType Type { get; }
```

### Örnekler

Yazı tipi kaynağı olarak bir yazı tipi dosyasındaki verilerle bir bayt dizisinin nasıl kullanılacağını gösterir.

```csharp
byte[] fontBytes = File.ReadAllBytes(MyDir + "Alte DIN 1451 Mittelschrift.ttf");
MemoryFontSource memoryFontSource = new MemoryFontSource(fontBytes, 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {memoryFontSource});

Assert.AreEqual(FontSourceType.MemoryFont, memoryFontSource.Type);
Assert.AreEqual(0, memoryFontSource.Priority);
```

### Ayrıca bakınız

* enum [FontSourceType](../../fontsourcetype/)
* class [MemoryFontSource](../)
* ad alanı [Aspose.Words.Fonts](../../memoryfontsource/)
* toplantı [Aspose.Words](../../../)


