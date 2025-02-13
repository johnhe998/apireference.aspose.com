---
title: Class FontInfoCollection
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Fonts.FontInfoCollection klas. Stellt eine Sammlung von Schriftarten dar die in einem Dokument verwendet werden.
type: docs
weight: 2750
url: /de/net/aspose.words.fonts/fontinfocollection/
---
## FontInfoCollection class

Stellt eine Sammlung von Schriftarten dar, die in einem Dokument verwendet werden.

```csharp
public class FontInfoCollection : IEnumerable<FontInfo>
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [Count](../../aspose.words.fonts/fontinfocollection/count/) { get; } | Ruft die Anzahl der in der Sammlung enthaltenen Elemente ab. |
| [EmbedSystemFonts](../../aspose.words.fonts/fontinfocollection/embedsystemfonts/) { get; set; } | Gibt an, ob Systemschriftarten in das Dokument eingebettet werden sollen oder nicht. Der Standardwert für diese Eigenschaft ist **FALSCH**. |
| [EmbedTrueTypeFonts](../../aspose.words.fonts/fontinfocollection/embedtruetypefonts/) { get; set; } | Gibt an, ob TrueType-Schriftarten in ein Dokument eingebettet werden, wenn es gespeichert wird. Der Standardwert für diese Eigenschaft ist **FALSCH** . |
| [Item](../../aspose.words.fonts/fontinfocollection/item/) { get; } | Ruft eine Schriftart mit dem angegebenen Namen ab. (2 indexers) |
| [SaveSubsetFonts](../../aspose.words.fonts/fontinfocollection/savesubsetfonts/) { get; set; } | Gibt an, ob eine Teilmenge der eingebetteten TrueType-Schriftarten mit dem Dokument gespeichert werden soll oder nicht. Der Standardwert für diese Eigenschaft ist **FALSCH**. |

## Methoden

| Name | Beschreibung |
| --- | --- |
| [Contains](../../aspose.words.fonts/fontinfocollection/contains/)(string) | Bestimmt, ob die Sammlung eine Schriftart mit dem angegebenen Namen enthält. |
| [GetEnumerator](../../aspose.words.fonts/fontinfocollection/getenumerator/)() | Gibt ein Aufzählungsobjekt zurück, das verwendet werden kann, um alle Elemente in der Sammlung zu durchlaufen. |

### Bemerkungen

Artikel sind[`FontInfo`](../fontinfo/) Objekte.

Sie erstellen keine Instanzen dieser Klasse direkt. Verwenden Sie die[`FontInfos`](../../aspose.words/documentbase/fontinfos/) -Eigenschaft, um auf die Sammlung von Schriftarten zuzugreifen, die im Dokument definiert sind.

### Beispiele

Zeigt, wie die Details zu den in einem Dokument vorhandenen Schriftarten gedruckt werden.

```csharp
Document doc = new Document(MyDir + "Embedded font.docx");

FontInfoCollection allFonts = doc.FontInfos;
// Drucken Sie alle verwendeten und nicht verwendeten Schriftarten im Dokument.
for (int i = 0; i < allFonts.Count; i++)
{
    Console.WriteLine($"Font index #{i}");
    Console.WriteLine($"\tName: {allFonts[i].Name}");
    Console.WriteLine($"\tIs {(allFonts[i].IsTrueType ? "" : "not ")}a trueType font");
}
```

Zeigt, wie ein Dokument mit eingebetteten TrueType-Schriftarten gespeichert wird.

```csharp
Document doc = new Document(MyDir + "Document.docx");

FontInfoCollection fontInfos = doc.FontInfos;
fontInfos.EmbedTrueTypeFonts = embedAllFonts;
fontInfos.EmbedSystemFonts = embedAllFonts;
fontInfos.SaveSubsetFonts = embedAllFonts;

doc.Save(ArtifactsDir + "Font.FontInfoCollection.docx");

if (embedAllFonts)
    Assert.That(25000, Is.LessThan(new FileInfo(ArtifactsDir + "Font.FontInfoCollection.docx").Length));
else
    Assert.That(15000, Is.AtLeast(new FileInfo(ArtifactsDir + "Font.FontInfoCollection.docx").Length));
```

### Siehe auch

* class [FontInfo](../fontinfo/)
* namensraum [Aspose.Words.Fonts](../../aspose.words.fonts/)
* Montage [Aspose.Words](../../)


