---
title: Class HeaderFooter
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.HeaderFooter 班级. 表示节的页眉或页脚文本的容器
type: docs
weight: 2920
url: /zh/net/aspose.words/headerfooter/
---
## HeaderFooter class

表示节的页眉或页脚文本的容器。

```csharp
public class HeaderFooter : Story
```

## 构造函数

| 姓名 | 描述 |
| --- | --- |
| [HeaderFooter](headerfooter/)(DocumentBase, HeaderFooterType) | 创建指定类型的新页眉或页脚。 |

## 特性

| 姓名 | 描述 |
| --- | --- |
| [ChildNodes](../../aspose.words/compositenode/childnodes/) { get; } | 获取该节点的所有直接子节点。 |
| [Count](../../aspose.words/compositenode/count/) { get; } | 获取此节点的直接子节点数。 |
| [CustomNodeId](../../aspose.words/node/customnodeid/) { get; set; } | 指定自定义节点标识符。 |
| virtual [Document](../../aspose.words/node/document/) { get; } | 获取该节点所属的文档。 |
| [FirstChild](../../aspose.words/compositenode/firstchild/) { get; } | 获取节点的第一个子节点。 |
| [FirstParagraph](../../aspose.words/story/firstparagraph/) { get; } | 获取故事的第一段。 |
| [HasChildNodes](../../aspose.words/compositenode/haschildnodes/) { get; } | 如果此节点有任何子节点，则返回 true。 |
| [HeaderFooterType](../../aspose.words/headerfooter/headerfootertype/) { get; } | 获取此页眉/页脚的类型。 |
| override [IsComposite](../../aspose.words/compositenode/iscomposite/) { get; } | 返回真，因为该节点可以有子节点。 |
| [IsHeader](../../aspose.words/headerfooter/isheader/) { get; } | 如果这个为真 **页眉页脚**对象是一个标题。 |
| [IsLinkedToPrevious](../../aspose.words/headerfooter/islinkedtoprevious/) { get; set; } | 如果此页眉或页脚链接到上一节中的相应页眉或页脚 ，则为真。 |
| [LastChild](../../aspose.words/compositenode/lastchild/) { get; } | 获取节点的最后一个子节点。 |
| [LastParagraph](../../aspose.words/story/lastparagraph/) { get; } | 获取故事的最后一段。 |
| [NextSibling](../../aspose.words/node/nextsibling/) { get; } | 获取紧跟此节点的节点。 |
| override [NodeType](../../aspose.words/headerfooter/nodetype/) { get; } | 返回 **NodeType.HeaderFooter**. |
| [Paragraphs](../../aspose.words/story/paragraphs/) { get; } | 获取作为故事直接子级的段落集合。 |
| [ParentNode](../../aspose.words/node/parentnode/) { get; } | 获取此节点的直接父节点。 |
| [ParentSection](../../aspose.words/headerfooter/parentsection/) { get; } | 获取此故事的父部分。 |
| [PreviousSibling](../../aspose.words/node/previoussibling/) { get; } | 获取紧接在此节点之前的节点。 |
| [Range](../../aspose.words/node/range/) { get; } | 返回一个 **范围**表示此节点中包含的文档部分的对象。 |
| [StoryType](../../aspose.words/story/storytype/) { get; } | 获取这个故事的类型。 |
| [Tables](../../aspose.words/story/tables/) { get; } | 获取作为故事直接子级的表的集合。 |

## 方法

| 姓名 | 描述 |
| --- | --- |
| override [Accept](../../aspose.words/headerfooter/accept/)(DocumentVisitor) | 接受访客。 |
| [AppendChild](../../aspose.words/compositenode/appendchild/)(Node) | 将指定节点添加到该节点的子节点列表的末尾。 |
| [AppendParagraph](../../aspose.words/story/appendparagraph/)(string) | 创建一个快捷方式[`Paragraph`](../paragraph/)带有可选文本的对象并将其附加到此对象的末尾。 |
| [Clone](../../aspose.words/node/clone/)(bool) | 创建节点的副本。 |
| [CreateNavigator](../../aspose.words/compositenode/createnavigator/)() | 保留供系统使用。 IXPathNavigable. |
| [DeleteShapes](../../aspose.words/story/deleteshapes/)() | 从这个故事的文本中删除所有形状。 |
| [GetAncestor](../../aspose.words/node/getancestor/)(NodeType) | 获取指定的第一个祖先[`NodeType`](../nodetype/). |
| [GetAncestor](../../aspose.words/node/getancestor/)(Type) | 获取指定对象类型的第一个祖先。 |
| [GetChild](../../aspose.words/compositenode/getchild/)(NodeType, int, bool) | 返回与指定类型匹配的第 N 个子节点。 |
| [GetChildNodes](../../aspose.words/compositenode/getchildnodes/)(NodeType, bool) | 返回与指定类型匹配的子节点的实时集合。 |
| [GetEnumerator](../../aspose.words/compositenode/getenumerator/)() | 为在该节点的子节点上的每个样式迭代提供支持。 |
| override [GetText](../../aspose.words/compositenode/gettext/)() | 获取该节点及其所有子节点的文本。 |
| [IndexOf](../../aspose.words/compositenode/indexof/)(Node) | 返回子节点数组中指定子节点的索引。 |
| [InsertAfter](../../aspose.words/compositenode/insertafter/)(Node, Node) | 在指定参考节点之后立即插入指定节点。 |
| [InsertBefore](../../aspose.words/compositenode/insertbefore/)(Node, Node) | 在指定的参考节点之前插入指定的节点。 |
| [NextPreOrder](../../aspose.words/node/nextpreorder/)(Node) | 根据前序树遍历算法获取下一个节点。 |
| [PrependChild](../../aspose.words/compositenode/prependchild/)(Node) | 将指定节点添加到此节点的子节点列表的开头。 |
| [PreviousPreOrder](../../aspose.words/node/previouspreorder/)(Node) | 根据前序树遍历算法获取上一个节点。 |
| [Remove](../../aspose.words/node/remove/)() | 从父级中移除自身。 |
| [RemoveAllChildren](../../aspose.words/compositenode/removeallchildren/)() | 移除当前节点的所有子节点。 |
| [RemoveChild](../../aspose.words/compositenode/removechild/)(Node) | 移除指定的子节点。 |
| [RemoveSmartTags](../../aspose.words/compositenode/removesmarttags/)() | 删除所有[`SmartTag`](../../aspose.words.markup/smarttag/)当前节点的后代节点。 |
| [SelectNodes](../../aspose.words/compositenode/selectnodes/)(string) | 选择与 XPath 表达式匹配的节点列表。 |
| [SelectSingleNode](../../aspose.words/compositenode/selectsinglenode/)(string) | 选择与 XPath 表达式匹配的第一个节点。 |
| [ToString](../../aspose.words/node/tostring/)(SaveFormat) | 将节点的内容导出为指定格式的字符串。 |
| [ToString](../../aspose.words/node/tostring/)(SaveOptions) | 使用指定的保存选项将节点的内容导出为字符串。 |

### 评论

**页眉页脚**可以包含 **段落**和 **桌子**子节点。

**页眉页脚**是节级节点，只能是 **部分** . 只能有一个 **页眉页脚**或每个[`HeaderFooterType`](./headerfootertype/)在一个 **部分**.

如果 **部分**没有 **页眉页脚**特定类型或 的 **页眉页脚**没有子节点，此页眉/页脚被认为链接到 Microsoft Word 中上一节相同类型的页眉/页脚。

什么时候 **页眉页脚**至少包含一个 **段落**，它不再 被认为与 Microsoft Word 中的先前链接。

### 例子

显示如何替换文档页脚中的文本。

```csharp
Document doc = new Document(MyDir + "Footer.docx");

HeaderFooterCollection headersFooters = doc.FirstSection.HeadersFooters;
HeaderFooter footer = headersFooters[HeaderFooterType.FooterPrimary];

FindReplaceOptions options = new FindReplaceOptions
{
    MatchCase = false,
    FindWholeWordsOnly = false
};

int currentYear = DateTime.Now.Year;
footer.Range.Replace("(C) 2006 Aspose Pty Ltd.", $"Copyright (C) {currentYear} by Aspose Pty Ltd.", options);

doc.Save(ArtifactsDir + "HeaderFooter.ReplaceText.docx");
```

显示如何从文档中删除所有页脚。

```csharp
Document doc = new Document(MyDir + "Header and footer types.docx");

// 遍历每个部分并删除各种页脚。
foreach (Section section in doc.OfType<Section>())
{
    // 共有三种页脚和页眉类型。
    // 1 - “第一个”页眉/页脚，仅出现在部分的第一页上。
    HeaderFooter footer = section.HeadersFooters[HeaderFooterType.FooterFirst];
    footer?.Remove();

    // 2 - “主要”页眉/页脚，出现在奇数页上。
    footer = section.HeadersFooters[HeaderFooterType.FooterPrimary];
    footer?.Remove();

     // 3 - “偶数”页眉/页脚，出现在偶数页上。
    footer = section.HeadersFooters[HeaderFooterType.FooterEven];
    footer?.Remove();

    Assert.AreEqual(0, section.HeadersFooters.Count(hf => !((HeaderFooter)hf).IsHeader));
}

doc.Save(ArtifactsDir + "HeaderFooter.RemoveFooters.docx");
```

显示如何创建页眉和页脚。

```csharp
Document doc = new Document();

// 创建一个标题并在其上附加一个段落。该段中的文字
// 将出现在本节每一页的顶部，主体文本上方。
HeaderFooter header = new HeaderFooter(doc, HeaderFooterType.HeaderPrimary);
doc.FirstSection.HeadersFooters.Add(header);

Paragraph para = header.AppendParagraph("My header.");

Assert.True(header.IsHeader);
Assert.True(para.IsEndOfHeaderFooter);

// 创建一个页脚并向其附加一个段落。该段中的文字
// 将出现在本节每一页的底部，主体文本下方。
HeaderFooter footer = new HeaderFooter(doc, HeaderFooterType.FooterPrimary);
doc.FirstSection.HeadersFooters.Add(footer);

para = footer.AppendParagraph("My footer.");

Assert.False(footer.IsHeader);
Assert.True(para.IsEndOfHeaderFooter);

Assert.AreEqual(footer, para.ParentStory);
Assert.AreEqual(footer.ParentSection, para.ParentSection);
Assert.AreEqual(footer.ParentSection, header.ParentSection);

doc.Save(ArtifactsDir + "HeaderFooter.Create.docx");
```

### 也可以看看

* class [Story](../story/)
* 命名空间 [Aspose.Words](../../aspose.words/)
* 部件 [Aspose.Words](../../)


