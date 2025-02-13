---
title: Enum TxtTrailingSpacesOptions
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Loading.TxtTrailingSpacesOptions 枚举. 指定在从导入期间处理尾随空格的可用选项Text文件.
type: docs
weight: 3540
url: /zh/net/aspose.words.loading/txttrailingspacesoptions/
---
## TxtTrailingSpacesOptions enumeration

指定在从导入期间处理尾随空格的可用选项Text文件.

```csharp
public enum TxtTrailingSpacesOptions
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| Trim | `0` |  |
| Preserve | `1` |  |

### 例子

显示在加载纯文本文档时如何修剪空白。

```csharp
string textDoc = "      Line 1 \n" +
                 "    Line 2   \n" +
                 " Line 3       ";

// 创建一个“TxtLoadOptions”对象，我们可以将它传递给文档的构造函数
// 修改我们加载纯文本文档的方式。
TxtLoadOptions loadOptions = new TxtLoadOptions();

// 将“LeadingSpacesOptions”属性设置为“TxtLeadingSpacesOptions.Preserve”
// 保留每行开头的所有空白字符。
// 将“LeadingSpacesOptions”属性设置为“TxtLeadingSpacesOptions.ConvertToIndent”
// 删除每行开头的所有空白字符，
// 然后对段落应用左首行缩进来模拟空格的效果。
// 将“LeadingSpacesOptions”属性设置为“TxtLeadingSpacesOptions.Trim”
// 删除每一行开头的所有空白字符。
loadOptions.LeadingSpacesOptions = txtLeadingSpacesOptions;

// 将“TrailingSpacesOptions”属性设置为“TxtTrailingSpacesOptions.Preserve”
// 保留每行末尾的所有空白字符。 
// 将“TrailingSpacesOptions”属性设置为“TxtTrailingSpacesOptions.Trim”以 
// 删除每行末尾的所有空白字符。
loadOptions.TrailingSpacesOptions = txtTrailingSpacesOptions;

Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

switch (txtLeadingSpacesOptions)
{
    case TxtLeadingSpacesOptions.ConvertToIndent:
        Assert.AreEqual(37.8d, paragraphs[0].ParagraphFormat.FirstLineIndent);
        Assert.AreEqual(25.2d, paragraphs[1].ParagraphFormat.FirstLineIndent);
        Assert.AreEqual(6.3d, paragraphs[2].ParagraphFormat.FirstLineIndent);

        Assert.True(paragraphs[0].GetText().StartsWith("Line 1"));
        Assert.True(paragraphs[1].GetText().StartsWith("Line 2"));
        Assert.True(paragraphs[2].GetText().StartsWith("Line 3"));
        break;
    case TxtLeadingSpacesOptions.Preserve:
        Assert.True(paragraphs.All(p => ((Paragraph)p).ParagraphFormat.FirstLineIndent == 0.0d));

        Assert.True(paragraphs[0].GetText().StartsWith("      Line 1"));
        Assert.True(paragraphs[1].GetText().StartsWith("    Line 2"));
        Assert.True(paragraphs[2].GetText().StartsWith(" Line 3"));
        break;
    case TxtLeadingSpacesOptions.Trim:
        Assert.True(paragraphs.All(p => ((Paragraph)p).ParagraphFormat.FirstLineIndent == 0.0d));

        Assert.True(paragraphs[0].GetText().StartsWith("Line 1"));
        Assert.True(paragraphs[1].GetText().StartsWith("Line 2"));
        Assert.True(paragraphs[2].GetText().StartsWith("Line 3"));
        break;
}

switch (txtTrailingSpacesOptions)
{
    case TxtTrailingSpacesOptions.Preserve:
        Assert.True(paragraphs[0].GetText().EndsWith("Line 1 \r"));
        Assert.True(paragraphs[1].GetText().EndsWith("Line 2   \r"));
        Assert.True(paragraphs[2].GetText().EndsWith("Line 3       \f"));
        break;
    case TxtTrailingSpacesOptions.Trim:
        Assert.True(paragraphs[0].GetText().EndsWith("Line 1\r"));
        Assert.True(paragraphs[1].GetText().EndsWith("Line 2\r"));
        Assert.True(paragraphs[2].GetText().EndsWith("Line 3\f"));
        break;
}
```

### 也可以看看

* 命名空间 [Aspose.Words.Loading](../../aspose.words.loading/)
* 部件 [Aspose.Words](../../)


