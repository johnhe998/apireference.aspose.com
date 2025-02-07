---
title: IMathFunction
second_title: Aspose.Slides for .NET API 参考
description: 指定参数的函数
type: docs
weight: 7560
url: /zh/net/aspose.slides.mathtext/imathfunction/
---
## IMathFunction interface

指定参数的函数。

```csharp
public interface IMathFunction : IMathElement
```

## 特性

| 姓名 | 描述 |
| --- | --- |
| [AsIMathElement](../../aspose.slides.mathtext/imathfunction/asimathelement) { get; } | 允许获取基础 IMathElement 接口 [`IMathElement`](../imathelement) |
| [Base](../../aspose.slides.mathtext/imathfunction/base) { get; } | 函数参数 |
| [Name](../../aspose.slides.mathtext/imathfunction/name) { get; } | 函数名 例如函数名是 sin 和 cos |

### 例子

示例:

```csharp
[C#]
IMathFunction sinX = new MathematicalText("sin").Function("x");
```

### 也可以看看

* interface [IMathElement](../imathelement)
* 命名空间 [Aspose.Slides.MathText](../../aspose.slides.mathtext)
* 部件 [Aspose.Slides](../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.Slides.dll -->
