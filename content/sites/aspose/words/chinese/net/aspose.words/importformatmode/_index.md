---
title: Enum ImportFormatMode
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.ImportFormatMode 枚举. 指定从另一个文档导入内容时如何合并格式
type: docs
weight: 3030
url: /zh/net/aspose.words/importformatmode/
---
## ImportFormatMode enumeration

指定从另一个文档导入内容时如何合并格式。

```csharp
public enum ImportFormatMode
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| UseDestinationStyles | `0` | 使用目标文档样式并复制新样式。这是默认选项。 |
| KeepSourceFormatting | `1` | 将所有需要的样式复制到目标文档，如果需要，生成唯一的样式名称。 |
| KeepDifferentStyles | `2` | 只复制与源文档中不同的样式。 |

### 评论

当您将节点从一个文档复制到另一个文档时，此选项指定当两个文档具有相同名称但格式不同的样式时如何解析formatting 。

格式解析如下：

1. 内置样式使用与区域设置无关的样式标识符进行匹配。 用户定义的样式使用区分大小写的样式名称进行匹配。
2. 如果在目标文档中没有找到匹配的样式，style （以及它引用的所有样式）将被复制到目标文档 中，并更新导入的节点以引用新的样式。
3. 如果目标文档中已经存在匹配的样式，那么会发生什么 取决于`导入格式模式`传递给 的参数[`Document.ImportNode`](../documentbase/importnode/) 如下所述。

使用时 **使用目的地样式**选项，如果目标文档中已经存在匹配样式 ，则不复制该样式，并且更新导入的节点 以引用现有样式。

使用的缺点 **使用目的地样式**是导入的文本可能 在目标文档中与源文档相比看起来不同。 例如，源文档中的“标题1”样式使用Arial 16pt字体， 目标文档中的“标题1”样式使用Times New Roman 14pt font. 当导入没有其他直接格式的“标题 1”样式的文本时，它将 在目标文档中显示为 Times New Roman 14pt 字体。

**保持SourceFormatting**选项允许确保导入的内容在目标文档中看起来与在源文档中的外观相同更改为 Normal目标文档中不存在。 在这种情况下，此类样式的格式将扩展为直接节点属性，以支持保留原始节点格式。

使用的缺点 **保持SourceFormatting**是如果您执行多个导入， 您最终可能会在目标文档中使用许多样式，这可能会使在 Microsoft Word 中使用 一致的样式格式对于该文档来说很困难。

使用 **保持不同风格**如果目标样式提供的格式与源文档中的样式相同，则选项允许重用目标样式 。 如果目标文档中的样式与源文件不同，则将其导入。

### 例子

演示如何将文档插入到另一个文档中。

```csharp
Document doc = new Document(MyDir + "Document.docx");

DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);

Document docToInsert = new Document(MyDir + "Formatted elements.docx");

builder.InsertDocument(docToInsert, ImportFormatMode.KeepSourceFormatting);
builder.Document.Save(ArtifactsDir + "DocumentBuilder.InsertDocument.docx");
```

### 也可以看看

* 命名空间 [Aspose.Words](../../aspose.words/)
* 部件 [Aspose.Words](../../)


