---
title: VbaModule.Type
second_title: Aspose.Words for .NET API 参考
description: VbaModule 财产. 指定模块是过程模块文档模块类模块还是设计器模块
type: docs
weight: 40
url: /zh/net/aspose.words.vba/vbamodule/type/
---
## VbaModule.Type property

指定模块是过程模块、文档模块、类模块还是设计器模块。

```csharp
public VbaModuleType Type { get; set; }
```

### 例子

演示如何使用宏创建 VBA 项目。

```csharp
Document doc = new Document();

// 创建一个新的 VBA 项目。
VbaProject project = new VbaProject();
project.Name = "Aspose.Project";
doc.VbaProject = project;

// 创建一个新模块并指定一个宏源代码。
VbaModule module = new VbaModule();
module.Name = "Aspose.Module";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New source code";

// 将模块添加到 VBA 项目。
doc.VbaProject.Modules.Add(module);

doc.Save(ArtifactsDir + "VbaProject.CreateVBAMacros.docm");
```

### 也可以看看

* enum [VbaModuleType](../../vbamoduletype/)
* class [VbaModule](../)
* 命名空间 [Aspose.Words.Vba](../../vbamodule/)
* 部件 [Aspose.Words](../../../)


