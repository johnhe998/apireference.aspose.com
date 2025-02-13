---
title: FileFontSource.Type
second_title: Aspose.Words för .NET API Referens
description: FileFontSource fast egendom. Returnerar typen av teckensnittskälla.
type: docs
weight: 40
url: /sv/net/aspose.words.fonts/filefontsource/type/
---
## FileFontSource.Type property

Returnerar typen av teckensnittskälla.

```csharp
public override FontSourceType Type { get; }
```

### Exempel

Visar hur man använder en teckensnittsfil i det lokala filsystemet som en teckensnittskälla.

```csharp
FileFontSource fileFontSource = new FileFontSource(MyDir + "Alte DIN 1451 Mittelschrift.ttf", 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {fileFontSource});

Assert.AreEqual(MyDir + "Alte DIN 1451 Mittelschrift.ttf", fileFontSource.FilePath);
Assert.AreEqual(FontSourceType.FontFile, fileFontSource.Type);
Assert.AreEqual(0, fileFontSource.Priority);
```

### Se även

* enum [FontSourceType](../../fontsourcetype/)
* class [FileFontSource](../)
* namnutrymme [Aspose.Words.Fonts](../../filefontsource/)
* hopsättning [Aspose.Words](../../../)


