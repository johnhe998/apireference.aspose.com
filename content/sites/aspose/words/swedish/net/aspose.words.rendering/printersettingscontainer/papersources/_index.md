---
title: PrinterSettingsContainer.PaperSources
second_title: Aspose.Words för .NET API Referens
description: PrinterSettingsContainer fast egendom. SePaperSources .
type: docs
weight: 40
url: /sv/net/aspose.words.rendering/printersettingscontainer/papersources/
---
## PrinterSettingsContainer.PaperSources property

SePaperSources .

```csharp
public PaperSourceCollection PaperSources { get; }
```

### Exempel

Visar hur du kommer åt och listar skrivarens papperskällor och storlekar.

```csharp
// "PrinterSettingsContainer" innehåller ett "PrinterSettings"-objekt,
// som innehåller unika data för olika skrivardrivrutiner.
PrinterSettingsContainer container = new PrinterSettingsContainer(new PrinterSettings());

Console.WriteLine($"This printer contains {container.PaperSources.Count} printer paper sources:");
foreach (PaperSource paperSource in container.PaperSources)
{
    bool isDefault = container.DefaultPageSettingsPaperSource.SourceName == paperSource.SourceName;
    Console.WriteLine($"\t{paperSource.SourceName}, " +
                      $"RawKind: {paperSource.RawKind} {(isDefault ? "(Default)" : "")}");
}

// Egenskapen "PaperSizes" innehåller listan över pappersstorlekar att instruera skrivaren att använda.
// Både PrinterSource och PrinterSize innehåller en "RawKind"-egenskap,
// vilket motsvarar en papperstyp som listas på PaperSourceKind enum.
// Om det finns en papperskälla med samma "RawKind"-värde som på den utskrivna sidan,
// skrivaren kommer att skriva ut sidan med den medföljande papperskällan och storleken.
// Annars kommer skrivaren som standard att använda den källa som anges av egenskapen "DefaultPageSettingsPaperSource".
Console.WriteLine($"{container.PaperSizes.Count} paper sizes:");
foreach (System.Drawing.Printing.PaperSize paperSize in container.PaperSizes)
{
    Console.WriteLine($"\t{paperSize}, RawKind: {paperSize.RawKind}");
}
```

### Se även

* class [PrinterSettingsContainer](../)
* namnutrymme [Aspose.Words.Rendering](../../printersettingscontainer/)
* hopsättning [Aspose.Words](../../../)


