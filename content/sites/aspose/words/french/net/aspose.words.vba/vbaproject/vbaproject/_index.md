---
title: VbaProject.VbaProject
second_title: Référence de l'API Aspose.Words pour .NET
description: VbaProject constructeur. Crée un VbaProject vide.
type: docs
weight: 10
url: /fr/net/aspose.words.vba/vbaproject/vbaproject/
---
## VbaProject constructor

Crée un VbaProject vide.

```csharp
public VbaProject()
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

* class [VbaProject](../)
* espace de noms [Aspose.Words.Vba](../../vbaproject/)
* Assemblée [Aspose.Words](../../../)


