---
title: VbaModuleCollection.Add
second_title: Aspose.Words لمراجع .NET API
description: VbaModuleCollection طريقة. يضيف وحدة نمطية إلى المجموعة.
type: docs
weight: 30
url: /ar/net/aspose.words.vba/vbamodulecollection/add/
---
## VbaModuleCollection.Add method

يضيف وحدة نمطية إلى المجموعة.

```csharp
public void Add(VbaModule vbaModule)
```

### أمثلة

يوضح كيفية إنشاء مشروع VBA باستخدام وحدات الماكرو.

```csharp
Document doc = new Document();

// إنشاء مشروع VBA جديد.
VbaProject project = new VbaProject();
project.Name = "Aspose.Project";
doc.VbaProject = project;

// إنشاء وحدة نمطية جديدة وتحديد شفرة مصدر الماكرو.
VbaModule module = new VbaModule();
module.Name = "Aspose.Module";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New source code";

// أضف الوحدة إلى مشروع VBA.
doc.VbaProject.Modules.Add(module);

doc.Save(ArtifactsDir + "VbaProject.CreateVBAMacros.docm");
```

### أنظر أيضا

* class [VbaModule](../../vbamodule/)
* class [VbaModuleCollection](../)
* مساحة الاسم [Aspose.Words.Vba](../../vbamodulecollection/)
* المجسم [Aspose.Words](../../../)


