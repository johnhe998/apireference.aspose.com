---
title: Enum TextWrapping
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Tables.TextWrapping 枚举. 指定文本在表格周围的环绕方式
type: docs
weight: 6080
url: /zh/net/aspose.words.tables/textwrapping/
---
## TextWrapping enumeration

指定文本在表格周围的环绕方式。

```csharp
public enum TextWrapping
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| None | `0` | 文本和表格按它们在文档中出现的顺序显示。 |
| Around | `1` | 文本环绕在表格周围，占用可用的侧面空间。 |
| Default | `0` | 默认值。 |

### 例子

展示如何使用表格文本换行。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Cell 1");
builder.InsertCell();
builder.Write("Cell 2");
builder.EndTable();
table.PreferredWidth = PreferredWidth.FromPoints(300);

builder.Font.Size = 16;
builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

// 将 "TextWrapping" 属性设置为 "TextWrapping.Around" 以使表格环绕它的文本，
// 并通过设置位置将其推入下面的段落。
table.TextWrapping = TextWrapping.Around;
table.AbsoluteHorizontalDistance = 100;
table.AbsoluteVerticalDistance = 20;

doc.Save(ArtifactsDir + "Table.WrapText.docx");
```

### 也可以看看

* 命名空间 [Aspose.Words.Tables](../../aspose.words.tables/)
* 部件 [Aspose.Words](../../)


