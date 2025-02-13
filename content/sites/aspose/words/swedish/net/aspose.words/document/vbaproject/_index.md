---
title: Document.VbaProject
second_title: Aspose.Words för .NET API Referens
description: Document fast egendom. Hämtar eller sätter enVbaProject .
type: docs
weight: 430
url: /sv/net/aspose.words/document/vbaproject/
---
## Document.VbaProject property

Hämtar eller sätter en`VbaProject` .

```csharp
public VbaProject VbaProject { get; set; }
```

### Exempel

Visar hur man kommer åt ett dokuments VBA-projektinformation.

```csharp
Document doc = new Document(MyDir + "VBA project.docm");

// Ett VBA-projekt innehåller en samling VBA-moduler.
VbaProject vbaProject = doc.VbaProject;
    ? $"Project name: {vbaProject.Name} signed; Project code page: {vbaProject.CodePage}; Modules count: {vbaProject.Modules.Count()}\n"
    : $"Project name: {vbaProject.Name} not signed; Project code page: {vbaProject.CodePage}; Modules count: {vbaProject.Modules.Count()}\n");

VbaModuleCollection vbaModules = doc.VbaProject.Modules; 

Assert.AreEqual(vbaModules.Count(), 3);

foreach (VbaModule module in vbaModules)
    Console.WriteLine($"Module name: {module.Name};\nModule code:\n{module.SourceCode}\n");

// Ställ in ny källkod för VBA-modulen. Du kan komma åt VBA-moduler i samlingen antingen med index eller namn.
vbaModules[0].SourceCode = "Your VBA code...";
vbaModules["Module1"].SourceCode = "Your VBA code...";

// Ta bort en modul från samlingen.
vbaModules.Remove(vbaModules[2]);
```

### Se även

* class [VbaProject](../../../aspose.words.vba/vbaproject/)
* class [Document](../)
* namnutrymme [Aspose.Words](../../document/)
* hopsättning [Aspose.Words](../../../)


