---
title: TxtLoadOptions.DetectNumberingWithWhitespaces
second_title: Aspose.Words for .NET API 参考
description: TxtLoadOptions 财产. 允许指定从纯文本格式导入文档时如何识别编号列表项 默认值为 true
type: docs
weight: 20
url: /zh/net/aspose.words.loading/txtloadoptions/detectnumberingwithwhitespaces/
---
## TxtLoadOptions.DetectNumberingWithWhitespaces property

允许指定从纯文本格式导入文档时如何识别编号列表项。 默认值为 true。

```csharp
public bool DetectNumberingWithWhitespaces { get; set; }
```

### 评论

如果此选项设置为 false，列表识别算法将检测列表段落，当列表编号以 结尾时，可以是点、右括号或项目符号（例如“•”、“*”、“-”或“o”）。

如果此选项设置为 true，则空格也用作列表编号分隔符： 用于阿拉伯风格编号（1.、1.1.2.）的列表识别算法同时使用空格和点（“.”）符号。

### 例子

显示如何在加载纯文本文档时检测列表。

```csharp
// 在字符串中创建一个纯文本文档，其中包含四个单独的部分，我们可以将其解释为列表，
// 使用不同的分隔符。将纯文本文档加载到“文档”对象中后，
// Aspose.Words 将始终检测前三个列表并添加一个“列表”对象
// 对于每个文档的“列表”属性。
const string textDoc = "Full stop delimiters:\n" +
                       "1. First list item 1\n" +
                       "2. First list item 2\n" +
                       "3. First list item 3\n\n" +
                       "Right bracket delimiters:\n" +
                       "1) Second list item 1\n" +
                       "2) Second list item 2\n" +
                       "3) Second list item 3\n\n" +
                       "Bullet delimiters:\n" +
                       "• Third list item 1\n" +
                       "• Third list item 2\n" +
                       "• Third list item 3\n\n" +
                       "Whitespace delimiters:\n" +
                       "1 Fourth list item 1\n" +
                       "2 Fourth list item 2\n" +
                       "3 Fourth list item 3";

// 创建一个“TxtLoadOptions”对象，我们可以将它传递给文档的构造函数
// 修改我们加载纯文本文档的方式。
TxtLoadOptions loadOptions = new TxtLoadOptions();

// 将“DetectNumberingWithWhitespaces”属性设置为“true”以检测编号项目
// 使用空格分隔符，例如我们文档中的第四个列表，作为列表。
// 这也可能错误地将以数字开头的段落检测为列表。
// 将“DetectNumberingWithWhitespaces”属性设置为“false”
// 不从带有空格分隔符的编号项目创建列表。
loadOptions.DetectNumberingWithWhitespaces = detectNumberingWithWhitespaces;

Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

if (detectNumberingWithWhitespaces)
{
    Assert.AreEqual(4, doc.Lists.Count);
    Assert.True(doc.FirstSection.Body.Paragraphs.Any(p => p.GetText().Contains("Fourth list") && ((Paragraph)p).IsListItem));
}
else
{
    Assert.AreEqual(3, doc.Lists.Count);
    Assert.False(doc.FirstSection.Body.Paragraphs.Any(p => p.GetText().Contains("Fourth list") && ((Paragraph)p).IsListItem));
}
```

### 也可以看看

* class [TxtLoadOptions](../)
* 命名空间 [Aspose.Words.Loading](../../txtloadoptions/)
* 部件 [Aspose.Words](../../../)


