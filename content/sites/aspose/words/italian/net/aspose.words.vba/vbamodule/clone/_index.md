---
title: VbaModule.Clone
second_title: Aspose.Words per .NET API Reference
description: VbaModule metodo. Esegue una copia diVbaModule .
type: docs
weight: 50
url: /it/net/aspose.words.vba/vbamodule/clone/
---
## VbaModule.Clone method

Esegue una copia di[`VbaModule`](../) .

```csharp
public VbaModule Clone()
```

### Valore di ritorno

Il VbaModule clonato.

### Esempi

Mostra come clonare in profondità un progetto e un modulo VBA.

```csharp
Document doc = new Document(MyDir + "VBA project.docm");
Document destDoc = new Document();

VbaProject copyVbaProject = doc.VbaProject.Clone();
destDoc.VbaProject = copyVbaProject;

// Nel documento di destinazione abbiamo già un modulo chiamato "Module1"
// perché l'abbiamo clonato insieme al progetto. Dovremo rimuovere il modulo.
VbaModule oldVbaModule = destDoc.VbaProject.Modules["Module1"];
VbaModule copyVbaModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Remove(oldVbaModule);
destDoc.VbaProject.Modules.Add(copyVbaModule);

destDoc.Save(ArtifactsDir + "VbaProject.CloneVbaProject.docm");
```

### Guarda anche

* class [VbaModule](../)
* spazio dei nomi [Aspose.Words.Vba](../../vbamodule/)
* assemblea [Aspose.Words](../../../)


