---
title: MemoryFontSource.FontData
second_title: Справочник по API Aspose.Words для .NET
description: MemoryFontSource свойство. Данные двоичного шрифта.
type: docs
weight: 30
url: /ru/net/aspose.words.fonts/memoryfontsource/fontdata/
---
## MemoryFontSource.FontData property

Данные двоичного шрифта.

```csharp
public byte[] FontData { get; }
```

### Примеры

Показывает, как использовать массив байтов с данными из файла шрифта в качестве источника шрифта.

```csharp
byte[] fontBytes = File.ReadAllBytes(MyDir + "Alte DIN 1451 Mittelschrift.ttf");
MemoryFontSource memoryFontSource = new MemoryFontSource(fontBytes, 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {memoryFontSource});

Assert.AreEqual(FontSourceType.MemoryFont, memoryFontSource.Type);
Assert.AreEqual(0, memoryFontSource.Priority);
```

### Смотрите также

* class [MemoryFontSource](../)
* пространство имен [Aspose.Words.Fonts](../../memoryfontsource/)
* сборка [Aspose.Words](../../../)


