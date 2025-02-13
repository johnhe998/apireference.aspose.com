---
title: Class StyleCollection
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.StyleCollection 班级. Style 对象的集合代表文档中的内置样式和用户定义的样式
type: docs
weight: 5840
url: /zh/net/aspose.words/stylecollection/
---
## StyleCollection class

Style 对象的集合，代表文档中的内置样式和用户定义的样式。

```csharp
public class StyleCollection : IEnumerable<Style>
```

## 特性

| 姓名 | 描述 |
| --- | --- |
| [Count](../../aspose.words/stylecollection/count/) { get; } | 获取集合中的样式数。 |
| [DefaultFont](../../aspose.words/stylecollection/defaultfont/) { get; } | 获取文档默认文本格式。 |
| [DefaultParagraphFormat](../../aspose.words/stylecollection/defaultparagraphformat/) { get; } | 获取文档默认段落格式。 |
| [Document](../../aspose.words/stylecollection/document/) { get; } | 获取所有者文档。 |
| [Item](../../aspose.words/stylecollection/item/) { get; } | 按名称或别名获取样式。 (3 indexers) |

## 方法

| 姓名 | 描述 |
| --- | --- |
| [Add](../../aspose.words/stylecollection/add/)(StyleType, string) | 创建一个新的用户定义样式并将其添加到集合中。 |
| [AddCopy](../../aspose.words/stylecollection/addcopy/)(Style) | 将样式复制到此集合中。 |
| [ClearQuickStyleGallery](../../aspose.words/stylecollection/clearquickstylegallery/)() | 从“快速样式库”面板中删除所有样式。 |
| [GetEnumerator](../../aspose.words/stylecollection/getenumerator/)() | 获取一个枚举器对象，该对象将按名称的字母顺序枚举样式。 |

### 例子

展示如何使用列表格式创建和使用段落样式。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 创建自定义段落样式。
Style style = doc.Styles.Add(StyleType.Paragraph, "MyStyle1");
style.Font.Size = 24;
style.Font.Name = "Verdana";
style.ParagraphFormat.SpaceAfter = 12;

// 创建一个列表并确保使用此样式的段落将使用此列表。
style.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDefault);
style.ListFormat.ListLevelNumber = 0;

// 将段落样式应用到文档构建器的当前段落，然后添加一些文本。
builder.ParagraphFormat.Style = style;
builder.Writeln("Hello World: MyStyle1, bulleted list.");

// 将文档构建器的样式更改为没有列表格式的样式并编写另一个段落。
builder.ParagraphFormat.Style = doc.Styles["Normal"];
builder.Writeln("Hello World: Normal.");

builder.Document.Save(ArtifactsDir + "Styles.ParagraphStyleBulletedList.docx");
```

### 也可以看看

* class [Style](../style/)
* 命名空间 [Aspose.Words](../../aspose.words/)
* 部件 [Aspose.Words](../../)


