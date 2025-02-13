---
title: VbaModuleCollection.Remove
second_title: Aspose.Words for .NET API 参考
description: VbaModuleCollection 方法. 从集合中删除指定的模块
type: docs
weight: 40
url: /zh/net/aspose.words.vba/vbamodulecollection/remove/
---
## VbaModuleCollection.Remove method

从集合中删除指定的模块。

```csharp
public void Remove(VbaModule module)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| module | VbaModule | 要移除的模块。 |

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

* class [VbaModule](../../vbamodule/)
* class [VbaModuleCollection](../)
* 命名空间 [Aspose.Words.Vba](../../vbamodulecollection/)
* 部件 [Aspose.Words](../../../)


