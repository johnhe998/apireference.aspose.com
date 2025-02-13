---
title: PrinterSettingsContainer.PaperSizes
second_title: Referencia de API de Aspose.Words para .NET
description: PrinterSettingsContainer propiedad. VerPaperSizes .
type: docs
weight: 30
url: /es/net/aspose.words.rendering/printersettingscontainer/papersizes/
---
## PrinterSettingsContainer.PaperSizes property

VerPaperSizes .

```csharp
public PaperSizeCollection PaperSizes { get; }
```

### Ejemplos

Muestra cómo acceder y enumerar las fuentes y tamaños de papel de su impresora.

```csharp
// El "PrinterSettingsContainer" contiene un objeto "PrinterSettings",
// que contiene datos únicos para diferentes controladores de impresora.
PrinterSettingsContainer container = new PrinterSettingsContainer(new PrinterSettings());

Console.WriteLine($"This printer contains {container.PaperSources.Count} printer paper sources:");
foreach (PaperSource paperSource in container.PaperSources)
{
    bool isDefault = container.DefaultPageSettingsPaperSource.SourceName == paperSource.SourceName;
    Console.WriteLine($"\t{paperSource.SourceName}, " +
                      $"RawKind: {paperSource.RawKind} {(isDefault ? "(Default)" : "")}");
}

// La propiedad "PaperSizes" contiene la lista de tamaños de papel para indicarle a la impresora que los use.
// Tanto PrinterSource como PrinterSize contienen una propiedad "RawKind",
// lo que equivale a un tipo de papel que figura en la enumeración PaperSourceKind.
// Si hay una fuente de papel con el mismo valor "RawKind" que el de la página de impresión,
// la impresora imprimirá la página utilizando la fuente y el tamaño de papel proporcionados.
// De lo contrario, la impresora utilizará de forma predeterminada el origen designado por la propiedad "DefaultPageSettingsPaperSource".
Console.WriteLine($"{container.PaperSizes.Count} paper sizes:");
foreach (System.Drawing.Printing.PaperSize paperSize in container.PaperSizes)
{
    Console.WriteLine($"\t{paperSize}, RawKind: {paperSize.RawKind}");
}
```

### Ver también

* class [PrinterSettingsContainer](../)
* espacio de nombres [Aspose.Words.Rendering](../../printersettingscontainer/)
* asamblea [Aspose.Words](../../../)


