---
title: PageRange.PageRange
second_title: Aspose.Words för .NET API Referens
description: PageRange byggare. Skapar ett nytt sidintervallsobjekt.
type: docs
weight: 10
url: /sv/net/aspose.words.saving/pagerange/pagerange/
---
## PageRange constructor

Skapar ett nytt sidintervallsobjekt.

```csharp
public PageRange(int from, int to)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| from | Int32 | Startsidan nollbaserat index. |
| to | Int32 | Slutsidans nollbaserat index. Om det överskrider indexet för den sista sidan i dokumentet, trunkeras det för att passa in i dokumentet vid rendering. |

### Anmärkningar

MaxValue betyder den sista sidan i dokumentet.

### Exempel

Visar hur man extraherar sidor baserat på exakta sidintervall.

```csharp
Document doc = new Document(MyDir + "Images.docx");

ImageSaveOptions imageOptions = new ImageSaveOptions(SaveFormat.Tiff);
PageSet pageSet = new PageSet(new PageRange(1, 1), new PageRange(2, 3), new PageRange(1, 3),
    new PageRange(2, 4), new PageRange(1, 1));

imageOptions.PageSet = pageSet;
doc.Save(ArtifactsDir + "ImageSaveOptions.ExportVariousPageRanges.tiff", imageOptions);
```

### Se även

* class [PageRange](../)
* namnutrymme [Aspose.Words.Saving](../../pagerange/)
* hopsättning [Aspose.Words](../../../)


