---
title: Section.ClearContent
second_title: Aspose.Words for .NET API 参考
description: Section 方法. 清除部分
type: docs
weight: 90
url: /zh/net/aspose.words/section/clearcontent/
---
## Section.ClearContent method

清除部分。

```csharp
public void ClearContent()
```

### 评论

的文本[`Body`](../body/)被清除，只剩下一个代表分节符的空段落。

所有页眉和页脚的文本都被清除，但[`HeaderFooter`](../../headerfooter/)对象本身不会被移除。

### 例子

显示如何清除节的内容。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Hello world!");

Assert.AreEqual("Hello world!", doc.GetText().Trim());
Assert.AreEqual(1, doc.FirstSection.Body.Paragraphs.Count);

// 运行“ClearContent”方法将删除所有部分内容
// 但留下一个空白段落以再次添加内容。
doc.FirstSection.ClearContent();

Assert.AreEqual(string.Empty, doc.GetText().Trim());
Assert.AreEqual(1, doc.FirstSection.Body.Paragraphs.Count);
```

### 也可以看看

* class [Section](../)
* 命名空间 [Aspose.Words](../../section/)
* 部件 [Aspose.Words](../../../)


