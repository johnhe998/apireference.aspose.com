---
title: PageInfo.PaperTray
second_title: Справочник по API Aspose.Words для .NET
description: PageInfo свойство. Получает лоток для бумаги лоток для этой страницы как указано в документе. Значение зависит от реализации принтера.
type: docs
weight: 40
url: /ru/net/aspose.words.rendering/pageinfo/papertray/
---
## PageInfo.PaperTray property

Получает лоток для бумаги (лоток) для этой страницы, как указано в документе. Значение зависит от реализации (принтера).

```csharp
public int PaperTray { get; }
```

### Примеры

Показывает, как печатать информацию о размере и ориентации каждой страницы в документе Word.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// В первом разделе 2 страницы. Каждому из них мы назначим отдельный лоток для бумаги принтера,
// чей номер будет соответствовать типу источника бумаги. Эти источники и их виды будут различаться
// в зависимости от установленного драйвера принтера.
PrinterSettings.PaperSourceCollection paperSources = new PrinterSettings().PaperSources;

doc.FirstSection.PageSetup.FirstPageTray = paperSources[0].RawKind;
doc.FirstSection.PageSetup.OtherPagesTray = paperSources[1].RawKind;

Console.WriteLine("Document \"{0}\" contains {1} pages.", doc.OriginalFileName, doc.PageCount);

float scale = 1.0f;
float dpi = 96;

for (int i = 0; i < doc.PageCount; i++)
{
    // Каждая страница имеет объект PageInfo, индексом которого является номер соответствующей страницы.
    PageInfo pageInfo = doc.GetPageInfo(i);

    // Печатаем ориентацию и размеры страницы.
    Console.WriteLine($"Page {i + 1}:");
    Console.WriteLine($"\tOrientation:\t{(pageInfo.Landscape ? "Landscape" : "Portrait")}");
    Console.WriteLine($"\tPaper size:\t\t{pageInfo.PaperSize} ({pageInfo.WidthInPoints:F0}x{pageInfo.HeightInPoints:F0}pt)");
    Console.WriteLine($"\tSize in points:\t{pageInfo.SizeInPoints}");
    Console.WriteLine($"\tSize in pixels:\t{pageInfo.GetSizeInPixels(1.0f, 96)} at {scale * 100}% scale, {dpi} dpi");

    // Печать информации об исходном лотке.
    Console.WriteLine($"\tTray:\t{pageInfo.PaperTray}");
    PaperSource source = pageInfo.GetSpecifiedPrinterPaperSource(paperSources, paperSources[0]);
    Console.WriteLine($"\tSuitable print source:\t{source.SourceName}, kind: {source.Kind}");
}
```

### Смотрите также

* class [PageInfo](../)
* пространство имен [Aspose.Words.Rendering](../../pageinfo/)
* сборка [Aspose.Words](../../../)


