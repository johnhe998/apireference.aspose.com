---
title: Class PrinterSettingsContainer
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Rendering.PrinterSettingsContainer klas. Repräsentiert einen Speicher für einige Parameter vonPrinterSettings Objekt.
type: docs
weight: 4320
url: /de/net/aspose.words.rendering/printersettingscontainer/
---
## PrinterSettingsContainer class

Repräsentiert einen Speicher für einige Parameter vonPrinterSettings Objekt.

```csharp
public class PrinterSettingsContainer
```

## Konstrukteure

| Name | Beschreibung |
| --- | --- |
| [PrinterSettingsContainer](printersettingscontainer/)(PrinterSettings) | Erstellt einen Container fürPrinterSettings . |

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [DefaultPageSettingsPaperSource](../../aspose.words.rendering/printersettingscontainer/defaultpagesettingspapersource/) { get; } | SiehePaperSource vonDefaultPageSettings . |
| [PaperSizes](../../aspose.words.rendering/printersettingscontainer/papersizes/) { get; } | SiehePaperSizes . |
| [PaperSources](../../aspose.words.rendering/printersettingscontainer/papersources/) { get; } | SiehePaperSources . |

### Bemerkungen

Zugriff auf Daten vonPrinterSettings dauert lange. `PrinterSettingsContainer` speichert Parameter vonPrinterSettings , damit das Drucken schneller funktioniert.

### Beispiele

Zeigt, wie Sie auf die Papierquellen und -formate Ihres Druckers zugreifen und diese auflisten.

```csharp
// Der "PrinterSettingsContainer" enthält ein "PrinterSettings"-Objekt,
// die eindeutige Daten für verschiedene Druckertreiber enthält.
PrinterSettingsContainer container = new PrinterSettingsContainer(new PrinterSettings());

Console.WriteLine($"This printer contains {container.PaperSources.Count} printer paper sources:");
foreach (PaperSource paperSource in container.PaperSources)
{
    bool isDefault = container.DefaultPageSettingsPaperSource.SourceName == paperSource.SourceName;
    Console.WriteLine($"\t{paperSource.SourceName}, " +
                      $"RawKind: {paperSource.RawKind} {(isDefault ? "(Default)" : "")}");
}

// Die Eigenschaft "PaperSizes" enthält die Liste der Papiergrößen, die der Drucker anweisen soll, zu verwenden.
// Sowohl PrinterSource als auch PrinterSize enthalten eine "RawKind"-Eigenschaft,
// was einem Papiertyp entspricht, der in der Aufzählung PaperSourceKind aufgeführt ist.
// Wenn es eine Papierquelle mit demselben "RawKind"-Wert wie der der Druckseite gibt,
// Der Drucker druckt die Seite mit der angegebenen Papierquelle und Größe.
// Andernfalls verwendet der Drucker standardmäßig die Quelle, die von der Eigenschaft "DefaultPageSettingsPaperSource" angegeben wird.
Console.WriteLine($"{container.PaperSizes.Count} paper sizes:");
foreach (System.Drawing.Printing.PaperSize paperSize in container.PaperSizes)
{
    Console.WriteLine($"\t{paperSize}, RawKind: {paperSize.RawKind}");
}
```

### Siehe auch

* namensraum [Aspose.Words.Rendering](../../aspose.words.rendering/)
* Montage [Aspose.Words](../../)


