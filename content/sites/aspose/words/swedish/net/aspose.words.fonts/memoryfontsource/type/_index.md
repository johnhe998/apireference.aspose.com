---
title: MemoryFontSource.Type
second_title: Aspose.Words för .NET API Referens
description: MemoryFontSource fast egendom. Returnerar typen av teckensnittskälla.
type: docs
weight: 40
url: /sv/net/aspose.words.fonts/memoryfontsource/type/
---
## MemoryFontSource.Type property

Returnerar typen av teckensnittskälla.

```csharp
public override FontSourceType Type { get; }
```

### Exempel

Visar hur man använder en byte-array med data från en teckensnittsfil som teckensnittskälla.

```csharp
byte[] fontBytes = File.ReadAllBytes(MyDir + "Alte DIN 1451 Mittelschrift.ttf");
MemoryFontSource memoryFontSource = new MemoryFontSource(fontBytes, 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {memoryFontSource});

Assert.AreEqual(FontSourceType.MemoryFont, memoryFontSource.Type);
Assert.AreEqual(0, memoryFontSource.Priority);
```

### Se även

* enum [FontSourceType](../../fontsourcetype/)
* class [MemoryFontSource](../)
* namnutrymme [Aspose.Words.Fonts](../../memoryfontsource/)
* hopsättning [Aspose.Words](../../../)


