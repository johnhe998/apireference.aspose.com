---
title: VbaModule.Type
second_title: Aspose.Words för .NET API Referens
description: VbaModule fast egendom. Anger om modulen är en procedurmodul dokumentmodul klassmodul eller designermodul.
type: docs
weight: 40
url: /sv/net/aspose.words.vba/vbamodule/type/
---
## VbaModule.Type property

Anger om modulen är en procedurmodul, dokumentmodul, klassmodul eller designermodul.

```csharp
public VbaModuleType Type { get; set; }
```

### Exempel

Visar hur man skapar ett VBA-projekt med hjälp av makron.

```csharp
Document doc = new Document();

// Skapa ett nytt VBA-projekt.
VbaProject project = new VbaProject();
project.Name = "Aspose.Project";
doc.VbaProject = project;

// Skapa en ny modul och ange en makrokällkod.
VbaModule module = new VbaModule();
module.Name = "Aspose.Module";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New source code";

// Lägg till modulen i VBA-projektet.
doc.VbaProject.Modules.Add(module);

doc.Save(ArtifactsDir + "VbaProject.CreateVBAMacros.docm");
```

### Se även

* enum [VbaModuleType](../../vbamoduletype/)
* class [VbaModule](../)
* namnutrymme [Aspose.Words.Vba](../../vbamodule/)
* hopsättning [Aspose.Words](../../../)


