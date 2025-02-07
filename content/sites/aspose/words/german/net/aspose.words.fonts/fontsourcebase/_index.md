---
title: Class FontSourceBase
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Fonts.FontSourceBase klas. Dies ist eine abstrakte Basisklasse für die Klassen die es dem Benutzer ermöglichen verschiedene Schriftartquellen anzugeben.
type: docs
weight: 2800
url: /de/net/aspose.words.fonts/fontsourcebase/
---
## FontSourceBase class

Dies ist eine abstrakte Basisklasse für die Klassen, die es dem Benutzer ermöglichen, verschiedene Schriftartquellen anzugeben.

```csharp
public abstract class FontSourceBase
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [Priority](../../aspose.words.fonts/fontsourcebase/priority/) { get; } | Gibt die Priorität der Schriftquelle zurück. |
| abstract [Type](../../aspose.words.fonts/fontsourcebase/type/) { get; } | Gibt den Typ der Schriftartquelle zurück. |
| [WarningCallback](../../aspose.words.fonts/fontsourcebase/warningcallback/) { get; set; } | Wird während der Verarbeitung der Schriftartquelle aufgerufen, wenn ein Problem erkannt wird, das zu einem Verlust der Formatierungstreue führen kann. |

## Methoden

| Name | Beschreibung |
| --- | --- |
| [GetAvailableFonts](../../aspose.words.fonts/fontsourcebase/getavailablefonts/)() | Gibt eine Liste der Schriftarten zurück, die über diese Quelle verfügbar sind. |

### Beispiele

Zeigt, wie eine Schriftartdatei im lokalen Dateisystem als Schriftartquelle verwendet wird.

```csharp
FileFontSource fileFontSource = new FileFontSource(MyDir + "Alte DIN 1451 Mittelschrift.ttf", 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {fileFontSource});

Assert.AreEqual(MyDir + "Alte DIN 1451 Mittelschrift.ttf", fileFontSource.FilePath);
Assert.AreEqual(FontSourceType.FontFile, fileFontSource.Type);
Assert.AreEqual(0, fileFontSource.Priority);
```

### Siehe auch

* namensraum [Aspose.Words.Fonts](../../aspose.words.fonts/)
* Montage [Aspose.Words](../../)


