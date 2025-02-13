---
title: Class PrinterSettingsContainer
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Rendering.PrinterSettingsContainer classe. Représente un stockage pour certains paramètres dePrinterSettings objet.
type: docs
weight: 4320
url: /fr/net/aspose.words.rendering/printersettingscontainer/
---
## PrinterSettingsContainer class

Représente un stockage pour certains paramètres dePrinterSettings objet.

```csharp
public class PrinterSettingsContainer
```

## Constructeurs

| Nom | La description |
| --- | --- |
| [PrinterSettingsContainer](printersettingscontainer/)(PrinterSettings) | Crée un conteneur pourPrinterSettings . |

## Propriétés

| Nom | La description |
| --- | --- |
| [DefaultPageSettingsPaperSource](../../aspose.words.rendering/printersettingscontainer/defaultpagesettingspapersource/) { get; } | VoirPaperSource deDefaultPageSettings . |
| [PaperSizes](../../aspose.words.rendering/printersettingscontainer/papersizes/) { get; } | VoirPaperSizes . |
| [PaperSources](../../aspose.words.rendering/printersettingscontainer/papersources/) { get; } | VoirPaperSources . |

### Remarques

Accès aux données dePrinterSettings prend beaucoup de temps. `PrinterSettingsContainer` met en cache les paramètres dePrinterSettings , pour que l'impression fonctionne plus rapidement.

### Exemples

Montre comment accéder et répertorier les sources et formats de papier de votre imprimante.

```csharp
// Le "PrinterSettingsContainer" contient un objet "PrinterSettings",
// qui contient des données uniques pour différents pilotes d'imprimante.
PrinterSettingsContainer container = new PrinterSettingsContainer(new PrinterSettings());

Console.WriteLine($"This printer contains {container.PaperSources.Count} printer paper sources:");
foreach (PaperSource paperSource in container.PaperSources)
{
    bool isDefault = container.DefaultPageSettingsPaperSource.SourceName == paperSource.SourceName;
    Console.WriteLine($"\t{paperSource.SourceName}, " +
                      $"RawKind: {paperSource.RawKind} {(isDefault ? "(Default)" : "")}");
}

// La propriété "PaperSizes" contient la liste des formats de papier à indiquer à l'imprimante à utiliser.
// Les deux PrinterSource et PrinterSize contiennent une propriété "RawKind",
// qui équivaut à un type de papier répertorié dans l'énumération PaperSourceKind.
// S'il existe une source papier avec la même valeur "RawKind" que celle de la page d'impression,
// l'imprimante imprimera la page en utilisant la source et le format de papier fournis.
// Sinon, l'imprimante utilisera par défaut la source désignée par la propriété "DefaultPageSettingsPaperSource".
Console.WriteLine($"{container.PaperSizes.Count} paper sizes:");
foreach (System.Drawing.Printing.PaperSize paperSize in container.PaperSizes)
{
    Console.WriteLine($"\t{paperSize}, RawKind: {paperSize.RawKind}");
}
```

### Voir également

* espace de noms [Aspose.Words.Rendering](../../aspose.words.rendering/)
* Assemblée [Aspose.Words](../../)


