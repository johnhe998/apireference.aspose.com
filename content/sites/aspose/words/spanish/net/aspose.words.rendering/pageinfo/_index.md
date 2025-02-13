---
title: Class PageInfo
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Rendering.PageInfo clase. Representa información sobre una página de documento en particular.
type: docs
weight: 4310
url: /es/net/aspose.words.rendering/pageinfo/
---
## PageInfo class

Representa información sobre una página de documento en particular.

```csharp
public class PageInfo
```

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [HeightInPoints](../../aspose.words.rendering/pageinfo/heightinpoints/) { get; } | Obtiene la altura de la página en puntos. |
| [Landscape](../../aspose.words.rendering/pageinfo/landscape/) { get; } | Devuelve verdadero si la orientación de la página especificada en el documento para esta página es horizontal. |
| [PaperSize](../../aspose.words.rendering/pageinfo/papersize/) { get; } | Obtiene el tamaño del papel como enumeración. |
| [PaperTray](../../aspose.words.rendering/pageinfo/papertray/) { get; } | Obtiene la bandeja de papel (bin) para esta página como se especifica en el documento. El valor es específico de la implementación (impresora). |
| [SizeInPoints](../../aspose.words.rendering/pageinfo/sizeinpoints/) { get; } | Obtiene el tamaño de la página en puntos. |
| [WidthInPoints](../../aspose.words.rendering/pageinfo/widthinpoints/) { get; } | Obtiene el ancho de la página en puntos. |

## Métodos

| Nombre | Descripción |
| --- | --- |
| [GetDotNetPaperSize](../../aspose.words.rendering/pageinfo/getdotnetpapersize/)(PaperSizeCollection) | Obtiene elPaperSize objeto adecuado para imprimir la página representada por este`PageInfo` . |
| [GetSizeInPixels](../../aspose.words.rendering/pageinfo/getsizeinpixels/#getsizeinpixels)(float, float) | Calcula el tamaño de la página en píxeles para un factor de zoom y una resolución específicos. |
| [GetSizeInPixels](../../aspose.words.rendering/pageinfo/getsizeinpixels/#getsizeinpixels_1)(float, float, float) | Calcula el tamaño de la página en píxeles para un factor de zoom y una resolución específicos. |
| [GetSpecifiedPrinterPaperSource](../../aspose.words.rendering/pageinfo/getspecifiedprinterpapersource/)(PaperSourceCollection, PaperSource) | Obtiene elPaperSource objeto adecuado para imprimir la página representada por este`PageInfo` . |

### Observaciones

El ancho y la altura de la página devueltos por este objeto representan el tamaño "final" de la página, por ejemplo, ya están girados a la orientación correcta.

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

* espacio de nombres [Aspose.Words.Rendering](../../aspose.words.rendering/)
* asamblea [Aspose.Words](../../)


