---
title: Enum FontSourceType
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Fonts.FontSourceType enum. Specifica il tipo di origine del carattere.
type: docs
weight: 2810
url: /it/net/aspose.words.fonts/fontsourcetype/
---
## FontSourceType enumeration

Specifica il tipo di origine del carattere.

```csharp
public enum FontSourceType
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| FontFile | `0` | A[`FileFontSource`](../filefontsource/) oggetto che rappresenta un singolo file di font. |
| FontsFolder | `1` | A[`FolderFontSource`](../folderfontsource/) oggetto che rappresenta la cartella con i file dei caratteri. |
| MemoryFont | `2` | A[`MemoryFontSource`](../memoryfontsource/) oggetto che rappresenta un singolo font in memoria. |
| SystemFonts | `3` | A[`SystemFontSource`](../systemfontsource/) oggetto che rappresenta tutti i font installati nel sistema. |
| FontStream | `4` | A[`StreamFontSource`](../streamfontsource/) oggetto che rappresenta un flusso con dati del carattere. |

### Esempi

Mostra come utilizzare un file di font nel file system locale come origine di font.

```csharp
FileFontSource fileFontSource = new FileFontSource(MyDir + "Alte DIN 1451 Mittelschrift.ttf", 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {fileFontSource});

Assert.AreEqual(MyDir + "Alte DIN 1451 Mittelschrift.ttf", fileFontSource.FilePath);
Assert.AreEqual(FontSourceType.FontFile, fileFontSource.Type);
Assert.AreEqual(0, fileFontSource.Priority);
```

### Guarda anche

* spazio dei nomi [Aspose.Words.Fonts](../../aspose.words.fonts/)
* assemblea [Aspose.Words](../../)


