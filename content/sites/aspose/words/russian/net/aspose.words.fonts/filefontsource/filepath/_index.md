---
title: FileFontSource.FilePath
second_title: Справочник по API Aspose.Words для .NET
description: FileFontSource свойство. Путь к файлу шрифта.
type: docs
weight: 30
url: /ru/net/aspose.words.fonts/filefontsource/filepath/
---
## FileFontSource.FilePath property

Путь к файлу шрифта.

```csharp
public string FilePath { get; }
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

* class [FileFontSource](../)
* пространство имен [Aspose.Words.Fonts](../../filefontsource/)
* сборка [Aspose.Words](../../../)


