---
title: VbaProject.Modules
second_title: Référence de l'API Aspose.Words pour .NET
description: VbaProject propriété. Renvoie la collection de modules de projet VBA.
type: docs
weight: 40
url: /fr/net/aspose.words.vba/vbaproject/modules/
---
## VbaProject.Modules property

Renvoie la collection de modules de projet VBA.

```csharp
public VbaModuleCollection Modules { get; }
```

### Exemples

Montre comment accéder aux informations de projet VBA d'un document.

```csharp
Document doc = new Document(MyDir + "VBA project.docm");

// Un projet VBA contient une collection de modules VBA.
VbaProject vbaProject = doc.VbaProject;
    ? $"Project name: {vbaProject.Name} signed; Project code page: {vbaProject.CodePage}; Modules count: {vbaProject.Modules.Count()}\n"
    : $"Project name: {vbaProject.Name} not signed; Project code page: {vbaProject.CodePage}; Modules count: {vbaProject.Modules.Count()}\n");

VbaModuleCollection vbaModules = doc.VbaProject.Modules; 

Assert.AreEqual(vbaModules.Count(), 3);

foreach (VbaModule module in vbaModules)
    Console.WriteLine($"Module name: {module.Name};\nModule code:\n{module.SourceCode}\n");

// Définit le nouveau code source pour le module VBA. Vous pouvez accéder aux modules VBA de la collection par index ou par nom.
vbaModules[0].SourceCode = "Your VBA code...";
vbaModules["Module1"].SourceCode = "Your VBA code...";

// Supprime un module de la collection.
vbaModules.Remove(vbaModules[2]);
```

### Voir également

* class [VbaModuleCollection](../../vbamodulecollection/)
* class [VbaProject](../)
* espace de noms [Aspose.Words.Vba](../../vbaproject/)
* Assemblée [Aspose.Words](../../../)


