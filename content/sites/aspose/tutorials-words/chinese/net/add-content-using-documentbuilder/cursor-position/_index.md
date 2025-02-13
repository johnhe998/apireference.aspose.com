---
title: 光标位置
linktitle: 光标位置
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 分步指南检索 Word 文档中的光标位置。
type: docs
weight: 10
url: /zh/net/add-content-using-documentbuilder/cursor-position/
---

在此分步示例中，您将使用 Aspose.Words for .NET 了解 Word 文档中的光标位置。我们将指导您完成整个过程，并为您提供必要的 C# 代码片段。在本指南结束时，您将能够检索文档中光标所在的当前节点和段落。

## 先决条件
在我们开始之前，请确保您满足以下先决条件：
- Aspose.Words for .NET 库安装在您的系统上。

## 第 1 步：创建新文档和 DocumentBuilder
首先，使用 Document 类创建一个新文档并初始化 DocumentBuilder 对象：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第2步：访问当前节点和段落
接下来，检索光标所在的当前节点和段落。这可以使用 DocumentBuilder 类的 CurrentNode 和 CurrentParagraph 属性来实现：

```csharp
Node curNode = builder.CurrentNode;
Paragraph curParagraph = builder.CurrentParagraph;
```

## 步骤 3：检索光标位置信息
现在，您可以检索有关光标位置的信息。在下面的代码片段中，我们打印当前段落的文本：

```csharp
Console.WriteLine("\nCursor move to paragraph: " + curParagraph.GetText());
```

### 使用 Aspose.Words for .NET 的光标位置示例源代码
以下是使用 Aspose.Words for .NET 了解光标位置的完整源代码：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Node curNode = builder.CurrentNode;
Paragraph curParagraph = builder.CurrentParagraph;

Console.WriteLine("\nCursor move to paragraph: " + curParagraph.GetText());
```

## 结论
恭喜！您已成功学习如何使用 Aspose.Words for .NET 在 Word 文档中处理光标位置。通过遵循分步指南并利用提供的源代码，您现在可以检索光标在文档中所在的当前节点和段落。

了解光标位置对于各种场景都很有用，例如根据光标位置操作文档内容或实现自定义编辑功能。

