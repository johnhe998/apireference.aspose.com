---
title: VbaProject.IsSigned
second_title: Aspose.Words for .NET API 参考
description: VbaProject 财产. 显示 VbaProject 是否已签名
type: docs
weight: 30
url: /zh/net/aspose.words.vba/vbaproject/issigned/
---
## VbaProject.IsSigned property

显示 VbaProject 是否已签名。

```csharp
public bool IsSigned { get; }
```

### 例子

显示如何访问文档的 VBA 项目信息。

```csharp
Document doc = new Document(MyDir + "VBA project.docm");

// VBA 项目包含 VBA 模块的集合。
VbaProject vbaProject = doc.VbaProject;
    ? $"Project name: {vbaProject.Name} signed; Project code page: {vbaProject.CodePage}; Modules count: {vbaProject.Modules.Count()}\n"
    : $"Project name: {vbaProject.Name} not signed; Project code page: {vbaProject.CodePage}; Modules count: {vbaProject.Modules.Count()}\n");

VbaModuleCollection vbaModules = doc.VbaProject.Modules; 

Assert.AreEqual(vbaModules.Count(), 3);

foreach (VbaModule module in vbaModules)
    Console.WriteLine($"Module name: {module.Name};\nModule code:\n{module.SourceCode}\n");

// 为 VBA 模块设置新的源代码。您可以通过索引或名称访问集合中的 VBA 模块。
vbaModules[0].SourceCode = "Your VBA code...";
vbaModules["Module1"].SourceCode = "Your VBA code...";

// 从集合中移除一个模块。
vbaModules.Remove(vbaModules[2]);
```

### 也可以看看

* class [VbaProject](../)
* 命名空间 [Aspose.Words.Vba](../../vbaproject/)
* 部件 [Aspose.Words](../../../)


