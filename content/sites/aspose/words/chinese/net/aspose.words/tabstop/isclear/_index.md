---
title: TabStop.IsClear
second_title: Aspose.Words for .NET API 参考
description: TabStop 财产. 如果此制表位清除此位置的任何现有制表位则返回 true
type: docs
weight: 30
url: /zh/net/aspose.words/tabstop/isclear/
---
## TabStop.IsClear property

如果此制表位清除此位置的任何现有制表位，则返回 true。

```csharp
public bool IsClear { get; }
```

### 例子

显示如何使用文档的制表位集合。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

TabStopCollection tabStops = builder.ParagraphFormat.TabStops;

// 72 磅是 Microsoft Word 制表位标尺上的一英寸。
tabStops.Add(new TabStop(72.0));
tabStops.Add(new TabStop(432.0, TabAlignment.Right, TabLeader.Dashes));

Assert.AreEqual(2, tabStops.Count);
Assert.IsFalse(tabStops[0].IsClear);
Assert.IsFalse(tabStops[0].Equals(tabStops[1]));

// 每个“制表符”字符将构建器的光标带到下一个制表位的位置。
builder.Writeln("Start\tTab 1\tTab 2");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

Assert.AreEqual(2, paragraphs.Count);

// 每个段落都有它的制表位集合，它从文档构建器的制表位集合中克隆它的值。
Assert.AreEqual(paragraphs[0].ParagraphFormat.TabStops, paragraphs[1].ParagraphFormat.TabStops);
Assert.AreNotSame(paragraphs[0].ParagraphFormat.TabStops, paragraphs[1].ParagraphFormat.TabStops);

// 制表位集合可以将我们指向特定位置之前和之后的 TabStops。
Assert.AreEqual(72.0, tabStops.Before(100.0).Position);
Assert.AreEqual(432.0, tabStops.After(100.0).Position);

// 我们可以清除段落的制表位集合以恢复默认的制表行为。
paragraphs[1].ParagraphFormat.TabStops.Clear();

Assert.AreEqual(0, paragraphs[1].ParagraphFormat.TabStops.Count);

doc.Save(ArtifactsDir + "TabStopCollection.TabStopCollection.docx");
```

### 也可以看看

* class [TabStop](../)
* 命名空间 [Aspose.Words](../../tabstop/)
* 部件 [Aspose.Words](../../../)


