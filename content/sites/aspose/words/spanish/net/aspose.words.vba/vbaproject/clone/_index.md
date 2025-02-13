---
title: VbaProject.Clone
second_title: Referencia de API de Aspose.Words para .NET
description: VbaProject método. Realiza una copia delVbaProject .
type: docs
weight: 70
url: /es/net/aspose.words.vba/vbaproject/clone/
---
## VbaProject.Clone method

Realiza una copia del[`VbaProject`](../) .

```csharp
public VbaProject Clone()
```

### Valor_devuelto

El VbaProject clonado.

### Ejemplos

Muestra cómo realizar una clonación profunda de un proyecto y un módulo de VBA.

```csharp
Document doc = new Document(MyDir + "VBA project.docm");
Document destDoc = new Document();

VbaProject copyVbaProject = doc.VbaProject.Clone();
destDoc.VbaProject = copyVbaProject;

// En el documento de destino, ya tenemos un módulo llamado "Module1"
// porque lo clonamos junto con el proyecto. Tendremos que quitar el módulo.
VbaModule oldVbaModule = destDoc.VbaProject.Modules["Module1"];
VbaModule copyVbaModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Remove(oldVbaModule);
destDoc.VbaProject.Modules.Add(copyVbaModule);

destDoc.Save(ArtifactsDir + "VbaProject.CloneVbaProject.docm");
```

### Ver también

* class [VbaProject](../)
* espacio de nombres [Aspose.Words.Vba](../../vbaproject/)
* asamblea [Aspose.Words](../../../)


