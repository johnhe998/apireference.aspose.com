---
title: PageInfo.PaperTray
second_title: Referencia de API de Aspose.Words para .NET
description: PageInfo propiedad. Obtiene la bandeja de papel bin para esta página como se especifica en el documento. El valor es específico de la implementación impresora.
type: docs
weight: 40
url: /es/net/aspose.words.rendering/pageinfo/papertray/
---
## PageInfo.PaperTray property

Obtiene la bandeja de papel (bin) para esta página como se especifica en el documento. El valor es específico de la implementación (impresora).

```csharp
public int PaperTray { get; }
```

### Ejemplos

Muestra cómo imprimir información sobre el tamaño y la orientación de la página para cada página de un documento de Word.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// La primera sección tiene 2 páginas. Asignaremos una bandeja de papel de impresora diferente a cada uno,
// cuyo número coincidirá con un tipo de fuente de papel. Estas fuentes y sus tipos variarán
// dependiendo del controlador de impresora instalado.
PrinterSettings.PaperSourceCollection paperSources = new PrinterSettings().PaperSources;

doc.FirstSection.PageSetup.FirstPageTray = paperSources[0].RawKind;
doc.FirstSection.PageSetup.OtherPagesTray = paperSources[1].RawKind;

Console.WriteLine("Document \"{0}\" contains {1} pages.", doc.OriginalFileName, doc.PageCount);

float scale = 1.0f;
float dpi = 96;

for (int i = 0; i < doc.PageCount; i++)
{
    // Cada página tiene un objeto PageInfo, cuyo índice es el número de la página respectiva.
    PageInfo pageInfo = doc.GetPageInfo(i);

    // Imprime la orientación y las dimensiones de la página.
    Console.WriteLine($"Page {i + 1}:");
    Console.WriteLine($"\tOrientation:\t{(pageInfo.Landscape ? "Landscape" : "Portrait")}");
    Console.WriteLine($"\tPaper size:\t\t{pageInfo.PaperSize} ({pageInfo.WidthInPoints:F0}x{pageInfo.HeightInPoints:F0}pt)");
    Console.WriteLine($"\tSize in points:\t{pageInfo.SizeInPoints}");
    Console.WriteLine($"\tSize in pixels:\t{pageInfo.GetSizeInPixels(1.0f, 96)} at {scale * 100}% scale, {dpi} dpi");

    // Imprimir la información de la bandeja de origen.
    Console.WriteLine($"\tTray:\t{pageInfo.PaperTray}");
    PaperSource source = pageInfo.GetSpecifiedPrinterPaperSource(paperSources, paperSources[0]);
    Console.WriteLine($"\tSuitable print source:\t{source.SourceName}, kind: {source.Kind}");
}
```

### Ver también

* class [PageInfo](../)
* espacio de nombres [Aspose.Words.Rendering](../../pageinfo/)
* asamblea [Aspose.Words](../../../)


