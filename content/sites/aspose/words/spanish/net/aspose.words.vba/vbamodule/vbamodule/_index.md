---
title: VbaModule.VbaModule
second_title: Referencia de API de Aspose.Words para .NET
description: VbaModule constructor. Crea un módulo vacío.
type: docs
weight: 10
url: /es/net/aspose.words.vba/vbamodule/vbamodule/
---
## VbaModule constructor

Crea un módulo vacío.

```csharp
public VbaModule()
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

* class [VbaModule](../)
* espacio de nombres [Aspose.Words.Vba](../../vbamodule/)
* asamblea [Aspose.Words](../../../)


