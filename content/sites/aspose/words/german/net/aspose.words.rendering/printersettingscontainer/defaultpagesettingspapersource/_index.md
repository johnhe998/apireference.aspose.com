---
title: PrinterSettingsContainer.DefaultPageSettingsPaperSource
second_title: Aspose.Words für .NET-API-Referenz
description: PrinterSettingsContainer eigendom. SiehePaperSource vonDefaultPageSettings .
type: docs
weight: 20
url: /de/net/aspose.words.rendering/printersettingscontainer/defaultpagesettingspapersource/
---
## PrinterSettingsContainer.DefaultPageSettingsPaperSource property

SiehePaperSource vonDefaultPageSettings .

```csharp
public PaperSource DefaultPageSettingsPaperSource { get; }
```

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

* class [PrinterSettingsContainer](../)
* namensraum [Aspose.Words.Rendering](../../printersettingscontainer/)
* Montage [Aspose.Words](../../../)


