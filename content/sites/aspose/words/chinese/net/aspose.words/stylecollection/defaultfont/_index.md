---
title: StyleCollection.DefaultFont
second_title: Aspose.Words for .NET API 参考
description: StyleCollection 财产. 获取文档默认文本格式
type: docs
weight: 20
url: /zh/net/aspose.words/stylecollection/defaultfont/
---
## StyleCollection.DefaultFont property

获取文档默认文本格式。

```csharp
public Font DefaultFont { get; }
```

### 评论

请注意，Microsoft Word 2007 中引入了文档范围的默认值，并且完全支持 OOXML 格式（Docx) only. 早期的文档格式对此功能的支持有限，只能存储字体名称。

### 例子

演示如何将样式添加到文档的样式集合。

```csharp
Document doc = new Document();
StyleCollection styles = doc.Styles;

// 为我们稍后可能添加到此集合中的新样式设置默认参数。
styles.DefaultFont.Name = "Courier New";

// 如果我们添加“StyleType.Paragraph”的样式，该集合将应用
// 将其“DefaultParagraphFormat”属性转换为样式的“ParagraphFormat”属性。
styles.DefaultParagraphFormat.FirstLineIndent = 15.0;

// 添加一个样式，然后验证它是否具有默认设置。
styles.Add(StyleType.Paragraph, "MyStyle");

Assert.AreEqual("Courier New", styles[4].Font.Name);
Assert.AreEqual(15.0, styles["MyStyle"].ParagraphFormat.FirstLineIndent);
```

### 也可以看看

* class [Font](../../font/)
* class [StyleCollection](../)
* 命名空间 [Aspose.Words](../../stylecollection/)
* 部件 [Aspose.Words](../../../)


