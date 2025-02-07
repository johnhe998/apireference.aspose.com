---
title: VbaModuleCollection.Add
second_title: Référence de l'API Aspose.Words pour .NET
description: VbaModuleCollection méthode. Ajoute un module à la collection.
type: docs
weight: 30
url: /fr/net/aspose.words.vba/vbamodulecollection/add/
---
## VbaModuleCollection.Add method

Ajoute un module à la collection.

```csharp
public void Add(VbaModule vbaModule)
```

### Exemples

Montre comment créer un projet VBA à l'aide de macros.

```csharp
Document doc = new Document();

// Crée un nouveau projet VBA.
VbaProject project = new VbaProject();
project.Name = "Aspose.Project";
doc.VbaProject = project;

// Crée un nouveau module et spécifie un code source de macro.
VbaModule module = new VbaModule();
module.Name = "Aspose.Module";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New source code";

// Ajoute le module au projet VBA.
doc.VbaProject.Modules.Add(module);

doc.Save(ArtifactsDir + "VbaProject.CreateVBAMacros.docm");
```

### Voir également

* class [VbaModule](../../vbamodule/)
* class [VbaModuleCollection](../)
* espace de noms [Aspose.Words.Vba](../../vbamodulecollection/)
* Assemblée [Aspose.Words](../../../)


