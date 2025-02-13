---
title: Class ComHelper
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.ComHelper 班级. 为 COM 客户端提供将文档加载到 Aspose.Words 的方法
type: docs
weight: 210
url: /zh/net/aspose.words/comhelper/
---
## ComHelper class

为 COM 客户端提供将文档加载到 Aspose.Words 的方法。

```csharp
public class ComHelper
```

## 构造函数

| 姓名 | 描述 |
| --- | --- |
| [ComHelper](comhelper/)() | 初始化这个类的一个新实例。 |

## 方法

| 姓名 | 描述 |
| --- | --- |
| [Open](../../aspose.words/comhelper/open/#open)(Stream) | 允许加载 COM 应用程序[`Document`](../document/)来自流. |
| [Open](../../aspose.words/comhelper/open/#open_1)(string) | 允许 COM 应用程序加载[`Document`](../document/)来自文件. |
| [OpenIStream](../../aspose.words/comhelper/openistream/)(IStream) | 允许 COM 应用程序加载[`Document`](../document/)来自 IStream 对象。 |

### 评论

使用`ComHelper`类将文档从文件或流加载到 [`Document`](../document/) COM 应用程序中的对象。

这[`Document`](../document/)类提供了一个默认构造函数来创建一个新的 document 并且还提供了重载的构造函数来从一个文件或流中加载一个文档。 如果你在一个 .NET 应用程序中使用 Aspose.Words，你可以使用所有的[`Document`](../document/) 直接构造函数，但如果您从 COM 应用程序使用 Aspose.Words， 仅是默认值[`Document`](../document/)构造函数可用。

### 例子

```csharp
[VBScript]

Dim helper
Set helper = CreateObject("Aspose.Words.ComHelper")

Dim doc
Set doc = helper.Open(fileName)
```

演示如何使用 ComHelper 类打开文档。

```csharp
// ComHelper 类允许我们从 COM 客户端加载文档。
ComHelper comHelper = new ComHelper();

// 1 - 使用本地系统文件名：
Document doc = comHelper.Open(MyDir + "Document.docx");

Assert.AreEqual("Hello World!\r\rHello Word!\r\r\rHello World!", doc.GetText().Trim());

// 2 - 从流中：
using (FileStream stream = new FileStream(MyDir + "Document.docx", FileMode.Open))
{
    doc = comHelper.Open(stream);

    Assert.AreEqual("Hello World!\r\rHello Word!\r\r\rHello World!", doc.GetText().Trim());
}
```

### 也可以看看

* 命名空间 [Aspose.Words](../../aspose.words/)
* 部件 [Aspose.Words](../../)


