---
title: MemoryFontSource.Type
second_title: Справочник по API Aspose.Words для .NET
description: MemoryFontSource свойство. Возвращает тип источника шрифта.
type: docs
weight: 40
url: /ru/net/aspose.words.fonts/memoryfontsource/type/
---
## MemoryFontSource.Type property

Возвращает тип источника шрифта.

```csharp
public override FontSourceType Type { get; }
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

* enum [FontSourceType](../../fontsourcetype/)
* class [MemoryFontSource](../)
* пространство имен [Aspose.Words.Fonts](../../memoryfontsource/)
* сборка [Aspose.Words](../../../)


