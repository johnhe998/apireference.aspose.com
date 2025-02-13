---
title: Style.Type
second_title: Aspose.Words for .NET API 参考
description: Style 财产. 获取样式类型段落或字符
type: docs
weight: 160
url: /zh/net/aspose.words/style/type/
---
## Style.Type property

获取样式类型（段落或字符）。

```csharp
public StyleType Type { get; }
```

### 例子

展示如何访问文档的样式集合。

```csharp
Document doc = new Document();

Assert.AreEqual(4, doc.Styles.Count);

// 枚举并列出使用 Aspose.Words 创建的文档默认包含的所有样式。
using (IEnumerator<Style> stylesEnum = doc.Styles.GetEnumerator())
{
    while (stylesEnum.MoveNext())
    {
        Style curStyle = stylesEnum.Current;
        Console.WriteLine($"Style name:\t\"{curStyle.Name}\", of type \"{curStyle.Type}\"");
        Console.WriteLine($"\tSubsequent style:\t{curStyle.NextParagraphStyleName}");
        Console.WriteLine($"\tIs heading:\t\t\t{curStyle.IsHeading}");
        Console.WriteLine($"\tIs QuickStyle:\t\t{curStyle.IsQuickStyle}");

        Assert.AreEqual(doc, curStyle.Document);
    }
}
```

### 也可以看看

* enum [StyleType](../../styletype/)
* class [Style](../)
* 命名空间 [Aspose.Words](../../style/)
* 部件 [Aspose.Words](../../../)


