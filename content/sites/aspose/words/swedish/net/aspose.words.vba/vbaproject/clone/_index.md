---
title: VbaProject.Clone
second_title: Aspose.Words för .NET API Referens
description: VbaProject metod. Utför en kopia avVbaProject .
type: docs
weight: 70
url: /sv/net/aspose.words.vba/vbaproject/clone/
---
## VbaProject.Clone method

Utför en kopia av[`VbaProject`](../) .

```csharp
public VbaProject Clone()
```

### Returvärde

Det klonade VbaProject.

### Exempel

Visar hur man djupklonar ett VBA-projekt och en modul.

```csharp
Document doc = new Document(MyDir + "VBA project.docm");
Document destDoc = new Document();

VbaProject copyVbaProject = doc.VbaProject.Clone();
destDoc.VbaProject = copyVbaProject;

// I destinationsdokumentet har vi redan en modul som heter "Module1"
// eftersom vi klonade det tillsammans med projektet. Vi kommer att behöva ta bort modulen.
VbaModule oldVbaModule = destDoc.VbaProject.Modules["Module1"];
VbaModule copyVbaModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Remove(oldVbaModule);
destDoc.VbaProject.Modules.Add(copyVbaModule);

destDoc.Save(ArtifactsDir + "VbaProject.CloneVbaProject.docm");
```

### Se även

* class [VbaProject](../)
* namnutrymme [Aspose.Words.Vba](../../vbaproject/)
* hopsättning [Aspose.Words](../../../)


