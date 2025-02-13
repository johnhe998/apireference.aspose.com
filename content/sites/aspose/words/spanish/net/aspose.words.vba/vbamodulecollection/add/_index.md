---
title: VbaModuleCollection.Add
second_title: Referencia de API de Aspose.Words para .NET
description: VbaModuleCollection método. Agrega un módulo a la colección.
type: docs
weight: 30
url: /es/net/aspose.words.vba/vbamodulecollection/add/
---
## VbaModuleCollection.Add method

Agrega un módulo a la colección.

```csharp
public void Add(VbaModule vbaModule)
```

### Ejemplos

Muestra cómo crear un proyecto VBA usando macros.

```csharp
Document doc = new Document();

// Crea un nuevo proyecto VBA.
VbaProject project = new VbaProject();
project.Name = "Aspose.Project";
doc.VbaProject = project;

// Crear un nuevo módulo y especificar un código fuente de macro.
VbaModule module = new VbaModule();
module.Name = "Aspose.Module";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New source code";

// Agregue el módulo al proyecto VBA.
doc.VbaProject.Modules.Add(module);

doc.Save(ArtifactsDir + "VbaProject.CreateVBAMacros.docm");
```

### Ver también

* class [VbaModule](../../vbamodule/)
* class [VbaModuleCollection](../)
* espacio de nombres [Aspose.Words.Vba](../../vbamodulecollection/)
* asamblea [Aspose.Words](../../../)


