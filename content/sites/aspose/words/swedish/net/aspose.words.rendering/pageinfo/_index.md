---
title: Class PageInfo
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Rendering.PageInfo klass. Representerar information om en viss dokumentsida.
type: docs
weight: 4310
url: /sv/net/aspose.words.rendering/pageinfo/
---
## PageInfo class

Representerar information om en viss dokumentsida.

```csharp
public class PageInfo
```

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [HeightInPoints](../../aspose.words.rendering/pageinfo/heightinpoints/) { get; } | Får sidans höjd i poäng. |
| [Landscape](../../aspose.words.rendering/pageinfo/landscape/) { get; } | Returnerar sant om sidorienteringen som anges i dokumentet för den här sidan är liggande. |
| [PaperSize](../../aspose.words.rendering/pageinfo/papersize/) { get; } | Hämtar pappersstorleken som uppräkning. |
| [PaperTray](../../aspose.words.rendering/pageinfo/papertray/) { get; } | Hämtar pappersfacket (fack) för den här sidan som specificerats i dokumentet. Värdet är implementerings(skrivar)specifikt. |
| [SizeInPoints](../../aspose.words.rendering/pageinfo/sizeinpoints/) { get; } | Får sidstorleken i poäng. |
| [WidthInPoints](../../aspose.words.rendering/pageinfo/widthinpoints/) { get; } | Hämtar sidans bredd i punkter. |

## Metoder

| namn | Beskrivning |
| --- | --- |
| [GetDotNetPaperSize](../../aspose.words.rendering/pageinfo/getdotnetpapersize/)(PaperSizeCollection) | FårPaperSize objekt som är lämpligt för utskrift sidan som representeras av detta`PageInfo` . |
| [GetSizeInPixels](../../aspose.words.rendering/pageinfo/getsizeinpixels/#getsizeinpixels)(float, float) | Beräknar sidstorleken i pixlar för en angiven zoomfaktor och upplösning. |
| [GetSizeInPixels](../../aspose.words.rendering/pageinfo/getsizeinpixels/#getsizeinpixels_1)(float, float, float) | Beräknar sidstorleken i pixlar för en angiven zoomfaktor och upplösning. |
| [GetSpecifiedPrinterPaperSource](../../aspose.words.rendering/pageinfo/getspecifiedprinterpapersource/)(PaperSourceCollection, PaperSource) | FårPaperSource objekt som är lämpligt för utskrift sidan som representeras av detta`PageInfo` . |

### Anmärkningar

Sidans bredd och höjd som returneras av detta objekt representerar den "slutliga" storleken på sidan, t.ex. är de redan roterade till korrekt orientering.

### Exempel

Visar hur du skriver ut information om sidstorlek och orientering för varje sida i ett Word-dokument.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Det första avsnittet har 2 sidor. Vi kommer att tilldela ett annat skrivarpappersfack till var och en,
// vars nummer kommer att matcha en sorts papperskälla. Dessa källor och deras slag kommer att variera
// beroende på den installerade skrivardrivrutinen.
PrinterSettings.PaperSourceCollection paperSources = new PrinterSettings().PaperSources;

doc.FirstSection.PageSetup.FirstPageTray = paperSources[0].RawKind;
doc.FirstSection.PageSetup.OtherPagesTray = paperSources[1].RawKind;

Console.WriteLine("Document \"{0}\" contains {1} pages.", doc.OriginalFileName, doc.PageCount);

float scale = 1.0f;
float dpi = 96;

for (int i = 0; i < doc.PageCount; i++)
{
    // Varje sida har ett PageInfo-objekt, vars index är respektive sidas nummer.
    PageInfo pageInfo = doc.GetPageInfo(i);

    // Skriv ut sidans orientering och mått.
    Console.WriteLine($"Page {i + 1}:");
    Console.WriteLine($"\tOrientation:\t{(pageInfo.Landscape ? "Landscape" : "Portrait")}");
    Console.WriteLine($"\tPaper size:\t\t{pageInfo.PaperSize} ({pageInfo.WidthInPoints:F0}x{pageInfo.HeightInPoints:F0}pt)");
    Console.WriteLine($"\tSize in points:\t{pageInfo.SizeInPoints}");
    Console.WriteLine($"\tSize in pixels:\t{pageInfo.GetSizeInPixels(1.0f, 96)} at {scale * 100}% scale, {dpi} dpi");

    // Skriv ut information om källfacket.
    Console.WriteLine($"\tTray:\t{pageInfo.PaperTray}");
    PaperSource source = pageInfo.GetSpecifiedPrinterPaperSource(paperSources, paperSources[0]);
    Console.WriteLine($"\tSuitable print source:\t{source.SourceName}, kind: {source.Kind}");
}
```

### Se även

* namnutrymme [Aspose.Words.Rendering](../../aspose.words.rendering/)
* hopsättning [Aspose.Words](../../)


