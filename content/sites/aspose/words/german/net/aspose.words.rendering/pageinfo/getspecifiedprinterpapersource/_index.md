---
title: PageInfo.GetSpecifiedPrinterPaperSource
second_title: Aspose.Words für .NET-API-Referenz
description: PageInfo methode. Ruft die abPaperSource Objekt das zum Drucken der von diesem repräsentierten Seite geeignet istPageInfo .
type: docs
weight: 90
url: /de/net/aspose.words.rendering/pageinfo/getspecifiedprinterpapersource/
---
## PageInfo.GetSpecifiedPrinterPaperSource method

Ruft die abPaperSource Objekt, das zum Drucken der von diesem repräsentierten Seite geeignet ist[`PageInfo`](../) .

```csharp
public PaperSource GetSpecifiedPrinterPaperSource(PaperSourceCollection paperSources, 
    PaperSource defaultPageSettingsPaperSource)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| paperSources | PaperSourceCollection | Verfügbare Papierquellen. |
| defaultPageSettingsPaperSource | PaperSource | In den Standarddruckereinstellungen definierte Papierquelle. |

### Rückgabewert

Ein Objekt, das Sie im .NET-Druckframework verwenden können, um die Papierquelle anzugeben.

### Bemerkungen

Diese Methode erfordert .NET Framework 2.0 oder höher.

### Beispiele

Zeigt, wie Informationen zur Seitengröße und Ausrichtung für jede Seite in einem Word-Dokument gedruckt werden.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Der erste Abschnitt hat 2 Seiten. Wir werden jedem einen anderen Druckerpapierschacht zuweisen,
// dessen Nummer mit einer Art Papierquelle übereinstimmt. Diese Quellen und ihre Arten variieren
// je nach installiertem Druckertreiber.
PrinterSettings.PaperSourceCollection paperSources = new PrinterSettings().PaperSources;

doc.FirstSection.PageSetup.FirstPageTray = paperSources[0].RawKind;
doc.FirstSection.PageSetup.OtherPagesTray = paperSources[1].RawKind;

Console.WriteLine("Document \"{0}\" contains {1} pages.", doc.OriginalFileName, doc.PageCount);

float scale = 1.0f;
float dpi = 96;

for (int i = 0; i < doc.PageCount; i++)
{
    // Jede Seite hat ein PageInfo-Objekt, dessen Index die Nummer der jeweiligen Seite ist.
    PageInfo pageInfo = doc.GetPageInfo(i);

    // Ausrichtung und Abmessungen der Seite drucken.
    Console.WriteLine($"Page {i + 1}:");
    Console.WriteLine($"\tOrientation:\t{(pageInfo.Landscape ? "Landscape" : "Portrait")}");
    Console.WriteLine($"\tPaper size:\t\t{pageInfo.PaperSize} ({pageInfo.WidthInPoints:F0}x{pageInfo.HeightInPoints:F0}pt)");
    Console.WriteLine($"\tSize in points:\t{pageInfo.SizeInPoints}");
    Console.WriteLine($"\tSize in pixels:\t{pageInfo.GetSizeInPixels(1.0f, 96)} at {scale * 100}% scale, {dpi} dpi");

    // Informationen zum Quellfach drucken.
    Console.WriteLine($"\tTray:\t{pageInfo.PaperTray}");
    PaperSource source = pageInfo.GetSpecifiedPrinterPaperSource(paperSources, paperSources[0]);
    Console.WriteLine($"\tSuitable print source:\t{source.SourceName}, kind: {source.Kind}");
}
```

### Siehe auch

* class [PageInfo](../)
* namensraum [Aspose.Words.Rendering](../../pageinfo/)
* Montage [Aspose.Words](../../../)


