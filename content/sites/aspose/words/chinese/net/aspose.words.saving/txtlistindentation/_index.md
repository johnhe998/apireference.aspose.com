---
title: Class TxtListIndentation
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Saving.TxtListIndentation 班级. 指定文档导出到时如何缩进列表级别Text格式.
type: docs
weight: 5370
url: /zh/net/aspose.words.saving/txtlistindentation/
---
## TxtListIndentation class

指定文档导出到时如何缩进列表级别Text格式.

```csharp
public class TxtListIndentation
```

## 构造函数

| 姓名 | 描述 |
| --- | --- |
| [TxtListIndentation](txtlistindentation/)() | 默认构造函数。 |

## 特性

| 姓名 | 描述 |
| --- | --- |
| [Character](../../aspose.words.saving/txtlistindentation/character/) { get; set; } | 获取或设置用于缩进列表级别的字符。 默认值为'\0'，表示没有缩进。 |
| [Count](../../aspose.words.saving/txtlistindentation/count/) { get; set; } | 获取或设置多少[`Character`](./character/)用作每个列表级别的缩进。 默认值为 0，这意味着没有缩进。 |

### 例子

显示在将文档保存为纯文本时如何配置列表缩进。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 创建一个具有三个缩进级别的列表。
builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Item 1");
builder.ListFormat.ListIndent();
builder.Writeln("Item 2");
builder.ListFormat.ListIndent(); 
builder.Write("Item 3");

// 创建一个“TxtSaveOptions”对象，我们可以将它传递给文档的“Save”方法
// 修改我们如何将文档保存为纯文本。
TxtSaveOptions txtSaveOptions = new TxtSaveOptions();

// 设置“Character”属性以分配要使用的字符
// 用于模拟明文列表缩进的填充。
txtSaveOptions.ListIndentation.Character = ' ';

// 设置“Count”属性指定次数
// 为每个列表缩进级别放置填充字符。
txtSaveOptions.ListIndentation.Count = 3;

doc.Save(ArtifactsDir + "TxtSaveOptions.TxtListIndentation.txt", txtSaveOptions);

string docText = File.ReadAllText(ArtifactsDir + "TxtSaveOptions.TxtListIndentation.txt");

Assert.AreEqual("1. Item 1\r\n" +
                "   a. Item 2\r\n" +
                "      i. Item 3\r\n", docText);
```

### 也可以看看

* 命名空间 [Aspose.Words.Saving](../../aspose.words.saving/)
* 部件 [Aspose.Words](../../)


