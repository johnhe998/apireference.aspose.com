---
title: VbaProject.CodePage
second_title: Aspose.Words für .NET-API-Referenz
description: VbaProject eigendom. Gibt die Codepage des VBAProjekts zurück.
type: docs
weight: 20
url: /de/net/aspose.words.vba/vbaproject/codepage/
---
## VbaProject.CodePage property

Gibt die Codepage des VBA-Projekts zurück.

```csharp
public int CodePage { get; }
```

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

* class [VbaProject](../)
* namensraum [Aspose.Words.Vba](../../vbaproject/)
* Montage [Aspose.Words](../../../)


