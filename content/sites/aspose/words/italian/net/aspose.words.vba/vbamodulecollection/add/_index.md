---
title: VbaModuleCollection.Add
second_title: Aspose.Words per .NET API Reference
description: VbaModuleCollection metodo. Aggiunge un modulo alla raccolta.
type: docs
weight: 30
url: /it/net/aspose.words.vba/vbamodulecollection/add/
---
## VbaModuleCollection.Add method

Aggiunge un modulo alla raccolta.

```csharp
public void Add(VbaModule vbaModule)
```

### Esempi

Mostra come creare un progetto VBA utilizzando le macro.

```csharp
Document doc = new Document();

// Crea un nuovo progetto VBA.
VbaProject project = new VbaProject();
project.Name = "Aspose.Project";
doc.VbaProject = project;

// Crea un nuovo modulo e specifica un codice sorgente della macro.
VbaModule module = new VbaModule();
module.Name = "Aspose.Module";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New source code";

// Aggiunge il modulo al progetto VBA.
doc.VbaProject.Modules.Add(module);

doc.Save(ArtifactsDir + "VbaProject.CreateVBAMacros.docm");
```

### Guarda anche

* class [VbaModule](../../vbamodule/)
* class [VbaModuleCollection](../)
* spazio dei nomi [Aspose.Words.Vba](../../vbamodulecollection/)
* assemblea [Aspose.Words](../../../)


