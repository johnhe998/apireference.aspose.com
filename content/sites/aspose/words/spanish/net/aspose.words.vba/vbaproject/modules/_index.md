---
title: VbaProject.Modules
second_title: Referencia de API de Aspose.Words para .NET
description: VbaProject propiedad. Devuelve la colección de módulos de proyecto de VBA.
type: docs
weight: 40
url: /es/net/aspose.words.vba/vbaproject/modules/
---
## VbaProject.Modules property

Devuelve la colección de módulos de proyecto de VBA.

```csharp
public VbaModuleCollection Modules { get; }
```

### Ejemplos

Muestra cómo acceder a la información del proyecto VBA de un documento.

```csharp
Document doc = new Document(MyDir + "VBA project.docm");

// Un proyecto VBA contiene una colección de módulos VBA.
VbaProject vbaProject = doc.VbaProject;
    ? $"Project name: {vbaProject.Name} signed; Project code page: {vbaProject.CodePage}; Modules count: {vbaProject.Modules.Count()}\n"
    : $"Project name: {vbaProject.Name} not signed; Project code page: {vbaProject.CodePage}; Modules count: {vbaProject.Modules.Count()}\n");

VbaModuleCollection vbaModules = doc.VbaProject.Modules; 

Assert.AreEqual(vbaModules.Count(), 3);

foreach (VbaModule module in vbaModules)
    Console.WriteLine($"Module name: {module.Name};\nModule code:\n{module.SourceCode}\n");

// Establecer nuevo código fuente para el módulo VBA. Puede acceder a los módulos de VBA en la colección por índice o por nombre.
vbaModules[0].SourceCode = "Your VBA code...";
vbaModules["Module1"].SourceCode = "Your VBA code...";

// Eliminar un módulo de la colección.
vbaModules.Remove(vbaModules[2]);
```

### Ver también

* class [VbaModuleCollection](../../vbamodulecollection/)
* class [VbaProject](../)
* espacio de nombres [Aspose.Words.Vba](../../vbaproject/)
* asamblea [Aspose.Words](../../../)


