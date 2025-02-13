---
title: ParagraphCollection.ToArray
second_title: Aspose.Words for .NET API 参考
description: ParagraphCollection 方法. 将集合中的所有段落复制到新的段落数组中
type: docs
weight: 20
url: /zh/net/aspose.words/paragraphcollection/toarray/
---
## ParagraphCollection.ToArray method

将集合中的所有段落复制到新的段落数组中。

```csharp
public Paragraph[] ToArray()
```

### 返回值

段落数组。

### 例子

演示如何从 NodeCollection 创建数组。

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");

Paragraph[] paras = doc.FirstSection.Body.Paragraphs.ToArray();

Assert.AreEqual(22, paras.Length);
```

展示如何在枚举期间使用“热移除”移除节点。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("The first paragraph");
builder.Writeln("The second paragraph");
builder.Writeln("The third paragraph");
builder.Writeln("The fourth paragraph");

// 在枚举中间从集合中删除一个节点。
foreach (Paragraph para in doc.FirstSection.Body.Paragraphs.ToArray())
    if (para.Range.Text.Contains("third"))
        para.Remove();

Assert.False(doc.GetText().Contains("The third paragraph"));
```

### 也可以看看

* class [Paragraph](../../paragraph/)
* class [ParagraphCollection](../)
* 命名空间 [Aspose.Words](../../paragraphcollection/)
* 部件 [Aspose.Words](../../../)


