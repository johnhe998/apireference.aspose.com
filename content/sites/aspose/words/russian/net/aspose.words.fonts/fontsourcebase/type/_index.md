---
title: FontSourceBase.Type
second_title: Справочник по API Aspose.Words для .NET
description: FontSourceBase свойство. Возвращает тип источника шрифта.
type: docs
weight: 20
url: /ru/net/aspose.words.fonts/fontsourcebase/type/
---
## FontSourceBase.Type property

Возвращает тип источника шрифта.

```csharp
public abstract FontSourceType Type { get; }
```

### Примеры

Показывает, как использовать файл шрифта в локальной файловой системе в качестве источника шрифта.

```csharp
FileFontSource fileFontSource = new FileFontSource(MyDir + "Alte DIN 1451 Mittelschrift.ttf", 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {fileFontSource});

Assert.AreEqual(MyDir + "Alte DIN 1451 Mittelschrift.ttf", fileFontSource.FilePath);
Assert.AreEqual(FontSourceType.FontFile, fileFontSource.Type);
Assert.AreEqual(0, fileFontSource.Priority);
```

### Смотрите также

* enum [FontSourceType](../../fontsourcetype/)
* class [FontSourceBase](../)
* пространство имен [Aspose.Words.Fonts](../../fontsourcebase/)
* сборка [Aspose.Words](../../../)


