---
title: ListLevel.LinkedStyle
second_title: Aspose.Words for .NET API 参考
description: ListLevel 财产. 获取或设置链接到此列表级别的段落样式
type: docs
weight: 60
url: /zh/net/aspose.words.lists/listlevel/linkedstyle/
---
## ListLevel.LinkedStyle property

获取或设置链接到此列表级别的段落样式。

```csharp
public Style LinkedStyle { get; set; }
```

### 评论

当列表级别未链接到段落样式时，此属性为 null。 此属性可以设置为 null。

### 例子

显示自定义列表标签的高级方法。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 列表允许我们用前缀符号和缩进组织和装饰段落集。
// 我们可以通过增加缩进级别来创建嵌套列表。 
// 我们可以使用文档构建器的“ListFormat”属性来开始和结束一个列表。 
// 我们在列表的开头和结尾之间添加的每个段落都将成为列表中的一个项目。
List list = doc.Lists.Add(ListTemplate.NumberDefault);

// 1 级标签将根据“标题 1”段落样式进行格式化，并带有前缀。
// 这些看起来像“附录 A”、“附录 B”...
list.ListLevels[0].NumberFormat = "Appendix \x0000";
list.ListLevels[0].NumberStyle = NumberStyle.UppercaseLetter;
list.ListLevels[0].LinkedStyle = doc.Styles["Heading 1"];

// 2 级标签将显示第一和第二列表级别的当前编号，并带有前导零。
// 如果第一个列表级别为 1，那么这些列表标签将看起来像“Section (1.01)”、“Section (1.02)”...
list.ListLevels[1].NumberFormat = "Section (\x0000.\x0001)";
list.ListLevels[1].NumberStyle = NumberStyle.LeadingZero;

// 注意高层使用大写字母编号。
// 我们可以将“IsLegal”属性设置为使用阿拉伯数字来表示更高的列表级别。
list.ListLevels[1].IsLegal = true;
list.ListLevels[1].RestartAfterLevel = 0;

// 3 级标签将是带有前缀和后缀的大写罗马数字，并将在每个 List 1 级项目处重新开始。
// 这些列表标签看起来像“-I-”、“-II-”...
list.ListLevels[2].NumberFormat = "-\x0002-";
list.ListLevels[2].NumberStyle = NumberStyle.UppercaseRoman;
list.ListLevels[2].RestartAfterLevel = 1;

// 使所有列表级别的标签加粗。
foreach (ListLevel level in list.ListLevels)
    level.Font.Bold = true;

// 将列表格式应用到当前段落。
builder.ListFormat.List = list;

// 创建将显示所有三个列表级别的列表项。
for (int n = 0; n < 2; n++)
{
    for (int i = 0; i < 3; i++)
    {
        builder.ListFormat.ListLevelNumber = i;
        builder.Writeln("Level " + i);
    }
}

builder.ListFormat.RemoveNumbers();

doc.Save(ArtifactsDir + "Lists.CreateListRestartAfterHigher.docx");
```

### 也可以看看

* class [Style](../../../aspose.words/style/)
* class [ListLevel](../)
* 命名空间 [Aspose.Words.Lists](../../listlevel/)
* 部件 [Aspose.Words](../../../)


