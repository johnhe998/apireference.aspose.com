---
title: Enum ListTrailingCharacter
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Lists.ListTrailingCharacter 枚举. 指定将列表标签与段落文本分开的字符
type: docs
weight: 3340
url: /zh/net/aspose.words.lists/listtrailingcharacter/
---
## ListTrailingCharacter enumeration

指定将列表标签与段落文本分开的字符。

```csharp
public enum ListTrailingCharacter
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| Tab | `0` | 在列表标签和段落文本之间放置一个制表符。 |
| Space | `1` | 在列表标签和段落文本之间放置一个空格字符。 |
| Nothing | `2` | 列表标签和段落文本之间没有分隔符。 |

### 评论

用作[`TrailingCharacter`](../listlevel/trailingcharacter/)财产。

### 例子

演示如何在使用 DocumentBuilder 时将自定义列表格式应用于段落。

```csharp
Document doc = new Document();

// 列表允许我们用前缀符号和缩进组织和装饰段落集。
// 我们可以通过增加缩进级别来创建嵌套列表。 
// 我们可以使用文档构建器的“ListFormat”属性来开始和结束一个列表。 
// 我们在列表的开头和结尾之间添加的每个段落都将成为列表中的一个项目。
// 从 Microsoft Word 模板创建一个列表，并自定义其前两个列表级别。
List list = doc.Lists.Add(ListTemplate.NumberDefault);

ListLevel listLevel = list.ListLevels[0];
listLevel.Font.Color = Color.Red;
listLevel.Font.Size = 24;
listLevel.NumberStyle = NumberStyle.OrdinalText;
listLevel.StartAt = 21;
listLevel.NumberFormat = "\x0000";

listLevel.NumberPosition = -36;
listLevel.TextPosition = 144;
listLevel.TabPosition = 144;

listLevel = list.ListLevels[1];
listLevel.Alignment = ListLevelAlignment.Right;
listLevel.NumberStyle = NumberStyle.Bullet;
listLevel.Font.Name = "Wingdings";
listLevel.Font.Color = Color.Blue;
listLevel.Font.Size = 24;

// 此 NumberFormat 值将创建星形项目符号列表符号。
listLevel.NumberFormat = "\xf0af";
listLevel.TrailingCharacter = ListTrailingCharacter.Space;
listLevel.NumberPosition = 144;

// 创建段落并将自定义列表格式的两个列表级别应用于它们。
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.List = list;
builder.Writeln("The quick brown fox...");
builder.Writeln("The quick brown fox...");

builder.ListFormat.ListIndent();
builder.Writeln("jumped over the lazy dog.");
builder.Writeln("jumped over the lazy dog.");

builder.ListFormat.ListOutdent();
builder.Writeln("The quick brown fox...");

builder.ListFormat.RemoveNumbers();

builder.Document.Save(ArtifactsDir + "Lists.CreateCustomList.docx");
```

### 也可以看看

* 命名空间 [Aspose.Words.Lists](../../aspose.words.lists/)
* 部件 [Aspose.Words](../../)


