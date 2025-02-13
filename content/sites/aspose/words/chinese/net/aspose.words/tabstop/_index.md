---
title: Class TabStop
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.TabStop 班级. 表示单个自定义制表位这 制表位对象是 the 的成员TabStopCollection集合.
type: docs
weight: 5900
url: /zh/net/aspose.words/tabstop/
---
## TabStop class

表示单个自定义制表位。这 **制表位**对象是 the 的成员[`TabStopCollection`](../tabstopcollection/)集合.

```csharp
public sealed class TabStop
```

## 构造函数

| 姓名 | 描述 |
| --- | --- |
| [TabStop](tabstop/#constructor)(double) | 初始化这个类的一个新实例。 |
| [TabStop](tabstop/#constructor_1)(double, TabAlignment, TabLeader) | 初始化这个类的一个新实例。 |

## 特性

| 姓名 | 描述 |
| --- | --- |
| [Alignment](../../aspose.words/tabstop/alignment/) { get; set; } | 获取或设置此制表位的文本对齐方式。 |
| [IsClear](../../aspose.words/tabstop/isclear/) { get; } | 如果此制表位清除此位置的任何现有制表位，则返回 true。 |
| [Leader](../../aspose.words/tabstop/leader/) { get; set; } | 获取或设置制表符下显示的引导线的类型。 |
| [Position](../../aspose.words/tabstop/position/) { get; } | 以点为单位获取制表位的位置。 |

## 方法

| 姓名 | 描述 |
| --- | --- |
| [Equals](../../aspose.words/tabstop/equals/#equals)(TabStop) | 与指定的 TabStop 比较。 |
| override [GetHashCode](../../aspose.words/tabstop/gethashcode/)() | 计算此对象的哈希码。 |

### 评论

通常，制表位指定制表位存在的位置。但是因为 制表位可以从父样式继承，所以子对象 可能需要明确定义在给定位置没有制表位。要在给定位置清除 继承的制表位，请创建一个 **制表位**对象和 set [`Alignment`](./alignment/)至`TabAlignment.Clear`.

有关更多信息，请参阅[`TabStopCollection`](../tabstopcollection/).

### 例子

显示如何修改 TOC 相关段落中右制表位的位置。

```csharp
Document doc = new Document(MyDir + "Table of contents.docx");

// 使用基于 TOC 结果的样式遍历所有段落；这是 TOC 和 TOC9 之间的任何样式。
foreach (Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true).OfType<Paragraph>())
    if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
        para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
    {
        // 获取本段使用的第一个选项卡，这应该是用于对齐页码的选项卡。
        TabStop tab = para.ParagraphFormat.TabStops[0];

        // 替换第一个默认制表符，用自定义制表位停止。
        para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
        para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
    }

doc.Save(ArtifactsDir + "Styles.ChangeTocsTabStops.docx");
```

### 也可以看看

* 命名空间 [Aspose.Words](../../aspose.words/)
* 部件 [Aspose.Words](../../)


