---
title: 插入文本输入表单字段
linktitle: 插入文本输入表单字段
second_title: Aspose.Words 文档处理 API
description: 通过此分步指南，了解如何使用 Aspose.Words for .NET 将文本输入表单字段插入到 Word 文档中。
type: docs
weight: 10
url: /zh/net/add-content-using-documentbuilder/insert-text-input-form-field/
---

在本分步指南中，我们将探索如何使用 Aspose.Words for .NET 中的插入文本输入表单字段功能，使用 C# 源代码在 Word 文档中添加和操作文本输入表单字段。文本输入表单字段允许用户在文档中输入自定义文本，使其成为创建交互式表单和调查问卷的理想选择。通过遵循以下说明，您将能够轻松地在文档中插入和自定义文本输入表单字段。让我们开始吧！

## Aspose.Words for .NET 中插入文本输入表单字段功能简介

Aspose.Words for .NET 中的插入文本输入表单字段功能允许您以编程方式向 Word 文档添加文本输入表单字段。这些表单字段提供了一个交互式元素，用户可以在其中输入自定义文本或数据。

## 了解使用该功能的要求

在继续实施之前，请确保您满足以下要求：

1. Aspose.Words for .NET 库安装在您的项目中。
2. C# 编程语言的基础知识。
3. 用于插入文本输入表单字段的现有 Word 文档或新文档。

确保满足这些先决条件才能顺利进行。

## 使用 C# 源代码实现插入文本输入表单字段的分步指南

请按照以下步骤使用提供的 C# 源代码实现插入文本输入表单字段功能：

### 步骤 1：初始化文档和文档生成器

首先，初始化文档和文档生成器。文档构建器是Aspose.Words for .NET提供的一个强大的工具，它允许我们以编程方式构建和操作Word文档。使用以下代码片段：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### 第 2 步：插入文本输入表单字段

接下来，我们将使用以下命令将文本输入表单字段插入到文档中`InsertTextInput`方法。该方法接受各种参数，包括表单字段的名称、表单字段的类型（在本例中为`TextFormFieldType.Regular`)、默认值和最大长度。这是一个例子：

```csharp
builder.InsertTextInput("TextInput", TextFormFieldType.Regular, "", "Hello", 0);
```

上面的代码将插入一个名为“TextInput”的文本输入表单字段，默认值为“Hello”，并且没有最大长度限制。

### 步骤 3：保存文档

插入文本输入表单字段后，使用以下命令将文档保存到所需位置`Save`方法。确保提供适当的文件路径：

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTextInputFormField.docx");
```

此代码将在指定位置保存带有插入文本输入表单字段的文档。

### 使用 Aspose.Words for .NET 插入文本输入表单字段的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertTextInput("TextInput", TextFormFieldType.Regular, "", "Hello", 0);

doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTextInputFormField.docx");
```
