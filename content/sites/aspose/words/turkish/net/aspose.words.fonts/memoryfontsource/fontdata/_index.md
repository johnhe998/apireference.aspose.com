---
title: MemoryFontSource.FontData
second_title: Aspose.Words for .NET API Referansı
description: MemoryFontSource mülk. İkili yazı tipi verileri.
type: docs
weight: 30
url: /tr/net/aspose.words.fonts/memoryfontsource/fontdata/
---
## MemoryFontSource.FontData property

İkili yazı tipi verileri.

```csharp
public byte[] FontData { get; }
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

* class [MemoryFontSource](../)
* ad alanı [Aspose.Words.Fonts](../../memoryfontsource/)
* toplantı [Aspose.Words](../../../)


