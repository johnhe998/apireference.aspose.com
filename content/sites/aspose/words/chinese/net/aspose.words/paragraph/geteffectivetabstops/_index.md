---
title: Paragraph.GetEffectiveTabStops
second_title: Aspose.Words for .NET API 参考
description: Paragraph 方法. 返回应用于此段落的所有制表位的数组包括由样式或列表间接应用的
type: docs
weight: 250
url: /zh/net/aspose.words/paragraph/geteffectivetabstops/
---
## Paragraph.GetEffectiveTabStops method

返回应用于此段落的所有制表位的数组，包括由样式或列表间接应用的。

```csharp
public TabStop[] GetEffectiveTabStops()
```

### 例子

显示如何为段落设置自定义制表位。

```csharp
Document doc = new Document();
Paragraph para = doc.FirstSection.Body.FirstParagraph;

// 如果我们在这个集合中没有制表位的段落中，
// 在 Microsoft Word 中，每按一次 Tab 键，光标就会跳 36 点。
Assert.AreEqual(0, doc.FirstSection.Body.FirstParagraph.GetEffectiveTabStops().Length);

// 如果我们通过“查看”选项卡启用标尺，我们可以在 Microsoft Word 中添加自定义制表位。
// 此标尺上的每个单位是两个默认制表位，即 72 磅。
// 我们可以像这样以编程方式添加自定义制表位。
TabStopCollection tabStops = doc.FirstSection.Body.FirstParagraph.ParagraphFormat.TabStops;
tabStops.Add(72, TabAlignment.Left, TabLeader.Dots);
tabStops.Add(216, TabAlignment.Center, TabLeader.Dashes);
tabStops.Add(360, TabAlignment.Right, TabLeader.Line);

// 通过“查看”启用标尺，我们可以在 Microsoft Word 中看到这些制表位 -> “显示”-> “统治者”。
Assert.AreEqual(3, para.GetEffectiveTabStops().Length);

// 我们添加的任何制表符都将使用标尺上的制表位，并且可能，
// 根据标签领导者的值，在标签出发和到达目的地之间留一条线。
para.AppendChild(new Run(doc, "\tTab 1\tTab 2\tTab 3"));

doc.Save(ArtifactsDir + "Paragraph.TabStops.docx");
```

### 也可以看看

* class [TabStop](../../tabstop/)
* class [Paragraph](../)
* 命名空间 [Aspose.Words](../../paragraph/)
* 部件 [Aspose.Words](../../../)


