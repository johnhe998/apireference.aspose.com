---
title: VbaModule.SourceCode
second_title: Aspose.Words für .NET-API-Referenz
description: VbaModule eigendom. Ruft den Quellcode des VBAProjektmoduls ab oder legt ihn fest.
type: docs
weight: 30
url: /de/net/aspose.words.vba/vbamodule/sourcecode/
---
## VbaModule.SourceCode property

Ruft den Quellcode des VBA-Projektmoduls ab oder legt ihn fest.

```csharp
public string SourceCode { get; set; }
```

### Beispiele

Zeigt, wie ein VBA-Projekt mithilfe von Makros erstellt wird.

```csharp
Document doc = new Document();

// Erstellen Sie ein neues VBA-Projekt.
VbaProject project = new VbaProject();
project.Name = "Aspose.Project";
doc.VbaProject = project;

// Erstellen Sie ein neues Modul und geben Sie einen Makroquellcode an.
VbaModule module = new VbaModule();
module.Name = "Aspose.Module";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New source code";

// Modul zum VBA-Projekt hinzufügen.
doc.VbaProject.Modules.Add(module);

doc.Save(ArtifactsDir + "VbaProject.CreateVBAMacros.docm");
```

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

* class [VbaModule](../)
* namensraum [Aspose.Words.Vba](../../vbamodule/)
* Montage [Aspose.Words](../../../)


