---
title: VbaModule.Type
second_title: Aspose.Words لمراجع .NET API
description: VbaModule ملكية. تحديد ما إذا كانت الوحدة النمطية هي وحدة نمطية إجرائية  أو وحدة مستند  أو وحدة فئة نمطية  أو وحدة مصمم.
type: docs
weight: 40
url: /ar/net/aspose.words.vba/vbamodule/type/
---
## VbaModule.Type property

تحديد ما إذا كانت الوحدة النمطية هي وحدة نمطية إجرائية ، أو وحدة مستند ، أو وحدة فئة نمطية ، أو وحدة مصمم.

```csharp
public VbaModuleType Type { get; set; }
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

* enum [VbaModuleType](../../vbamoduletype/)
* class [VbaModule](../)
* مساحة الاسم [Aspose.Words.Vba](../../vbamodule/)
* المجسم [Aspose.Words](../../../)


