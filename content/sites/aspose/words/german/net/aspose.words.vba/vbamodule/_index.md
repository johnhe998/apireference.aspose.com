---
title: Class VbaModule
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Vba.VbaModule klas. Bietet Zugriff auf das VBAProjektmodul.
type: docs
weight: 6240
url: /de/net/aspose.words.vba/vbamodule/
---
## VbaModule class

Bietet Zugriff auf das VBA-Projektmodul.

```csharp
public class VbaModule
```

## Konstrukteure

| Name | Beschreibung |
| --- | --- |
| [VbaModule](vbamodule/)() | Erstellt ein leeres Modul. |

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [Name](../../aspose.words.vba/vbamodule/name/) { get; set; } | Ruft den Namen des VBA-Projektmoduls ab oder legt ihn fest. |
| [SourceCode](../../aspose.words.vba/vbamodule/sourcecode/) { get; set; } | Ruft den Quellcode des VBA-Projektmoduls ab oder legt ihn fest. |
| [Type](../../aspose.words.vba/vbamodule/type/) { get; set; } | Gibt an, ob das Modul ein prozedurales Modul, Dokumentmodul, Klassenmodul oder Designermodul ist. |

## Methoden

| Name | Beschreibung |
| --- | --- |
| [Clone](../../aspose.words.vba/vbamodule/clone/)() | Führt eine Kopie der`VbaModule` . |

### Beispiele

Zeigt, wie auf die VBA-Projektinformationen eines Dokuments zugegriffen wird.

```csharp
Document doc = new Document(MyDir + "VBA project.docm");

// Ein VBA-Projekt enthält eine Sammlung von VBA-Modulen.
VbaProject vbaProject = doc.VbaProject;
    ? $"Project name: {vbaProject.Name} signed; Project code page: {vbaProject.CodePage}; Modules count: {vbaProject.Modules.Count()}\n"
    : $"Project name: {vbaProject.Name} not signed; Project code page: {vbaProject.CodePage}; Modules count: {vbaProject.Modules.Count()}\n");

VbaModuleCollection vbaModules = doc.VbaProject.Modules; 

Assert.AreEqual(vbaModules.Count(), 3);

foreach (VbaModule module in vbaModules)
    Console.WriteLine($"Module name: {module.Name};\nModule code:\n{module.SourceCode}\n");

// Neuen Quellcode für VBA-Modul setzen. Sie können auf VBA-Module in der Sammlung entweder nach Index oder nach Name zugreifen.
vbaModules[0].SourceCode = "Your VBA code...";
vbaModules["Module1"].SourceCode = "Your VBA code...";

// Ein Modul aus der Sammlung entfernen.
vbaModules.Remove(vbaModules[2]);
```

### Siehe auch

* namensraum [Aspose.Words.Vba](../../aspose.words.vba/)
* Montage [Aspose.Words](../../)


