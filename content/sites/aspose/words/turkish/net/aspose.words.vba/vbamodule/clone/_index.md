---
title: VbaModule.Clone
second_title: Aspose.Words for .NET API Referansı
description: VbaModule yöntem. VbaModule .
type: docs
weight: 50
url: /tr/net/aspose.words.vba/vbamodule/clone/
---
## VbaModule.Clone method

[`VbaModule`](../) .

```csharp
public VbaModule Clone()
```

### Geri dönüş değeri

Klonlanmış VbaModule.

### Örnekler

Bir VBA projesinin ve modülünün nasıl derin klonlanacağını gösterir.

```csharp
Document doc = new Document(MyDir + "VBA project.docm");
Document destDoc = new Document();

VbaProject copyVbaProject = doc.VbaProject.Clone();
destDoc.VbaProject = copyVbaProject;

// Hedef belgede zaten "Module1" adında bir modülümüz var
// çünkü onu projeyle birlikte klonladık. Modülü çıkarmamız gerekecek.
VbaModule oldVbaModule = destDoc.VbaProject.Modules["Module1"];
VbaModule copyVbaModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Remove(oldVbaModule);
destDoc.VbaProject.Modules.Add(copyVbaModule);

destDoc.Save(ArtifactsDir + "VbaProject.CloneVbaProject.docm");
```

### Ayrıca bakınız

* class [VbaModule](../)
* ad alanı [Aspose.Words.Vba](../../vbamodule/)
* toplantı [Aspose.Words](../../../)


