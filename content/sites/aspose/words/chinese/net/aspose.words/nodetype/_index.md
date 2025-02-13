---
title: Enum NodeType
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.NodeType 枚举. 指定 Word 文档节点的类型
type: docs
weight: 3990
url: /zh/net/aspose.words/nodetype/
---
## NodeType enumeration

指定 Word 文档节点的类型。

```csharp
public enum NodeType
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| Any | `0` | 表示所有节点类型。允许选择所有孩子。 |
| Document | `1` | 一个[`Document`](../document/)对象，作为文档树的根， 提供对整个 Word 文档的访问。 |
| Section | `2` | 一个[`Section`](../section/)对应于 Word 文档中的一个部分的对象。 |
| Body | `3` | 一个[`Body`](../body/)包含部分正文（正文故事）的对象。 |
| HeaderFooter | `4` | 一个[`HeaderFooter`](../headerfooter/)包含节内特定页眉或页脚文本的对象。 |
| Table | `5` | 一个[`Table`](../../aspose.words.tables/table/)表示 Word 文档中的表格的对象。 |
| Row | `6` | 一排桌子。 |
| Cell | `7` | 表格行的单元格。 |
| Paragraph | `8` | 一段文字。 |
| BookmarkStart | `9` | 书签标记的开头。 |
| BookmarkEnd | `10` | 书签标记的结束。 |
| EditableRangeStart | `11` | 可编辑范围的开始。 |
| EditableRangeEnd | `12` | 可编辑范围的结束。 |
| MoveFromRangeStart | `13` | MoveFrom 范围的开始。 |
| MoveFromRangeEnd | `14` | MoveFrom 范围的结束。 |
| MoveToRangeStart | `15` | MoveTo 范围的开始。 |
| MoveToRangeEnd | `16` | MoveTo 范围的结束。 |
| GroupShape | `17` | 一组形状、图像、OLE 对象或其他组形状。 |
| Shape | `18` | 绘图对象，例如 OfficeArt 形状、图像或 OLE 对象。 |
| Comment | `19` | Word 文档中的注释。 |
| Footnote | `20` | Word 文档中的脚注或尾注。 |
| Run | `21` | 一段文字。 |
| FieldStart | `22` | 一个特殊字符，用于指定 Word 字段的开头。 |
| FieldSeparator | `23` | 将域代码与域结果分开的特殊字符。 |
| FieldEnd | `24` | 一个特殊字符，用于指定 Word 字段的结尾。 |
| FormField | `25` | 一个表单域。 |
| SpecialChar | `26` | 不是更具体的特殊字符类型之一的特殊字符。 |
| SmartTag | `27` | 围绕段落中一个或多个内联结构（运行、图像、字段等）的智能标记 |
| StructuredDocumentTag | `28` | 允许定义客户特定的信息及其呈现方式。 |
| StructuredDocumentTagRangeStart | `29` | 一个开始 **远程**接受多节内容的结构化文档标签。 |
| StructuredDocumentTagRangeEnd | `30` | 一个结束 **远程**接受多节内容的结构化文档标签。 |
| GlossaryDocument | `31` | 主文档中的词汇表文档。 |
| BuildingBlock | `32` | 词汇表文档中的构建块（例如词汇表文档条目）。 |
| CommentRangeStart | `33` | 表示注释范围开始的标记节点。 |
| CommentRangeEnd | `34` | 表示注释范围结束的标记节点。 |
| OfficeMath | `35` | 一个 Office Math 对象。可以是方程、函数、矩阵或其他数学对象之一。 可以是数学对象的集合，也可以包含一些非数学对象，例如文本。 |
| SubDocument | `36` | 一个子文档节点，它是指向另一个文档的链接。 |
| System | `37` | 保留供 Aspose.Words 内部使用。 |
| Null | `38` | 保留供 Aspose.Words 内部使用。 |

### 例子

显示如何遍历复合节点的子节点集合。

```csharp
Document doc = new Document();

// 将两个运行和一个形状作为子节点添加到该文档的第一段。
Paragraph paragraph = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);
paragraph.AppendChild(new Run(doc, "Hello world! "));

Shape shape = new Shape(doc, ShapeType.Rectangle);
shape.Width = 200;
shape.Height = 200;
// 请注意，'CustomNodeId' 不会保存到输出文件中，并且仅在节点生命周期内存在。
shape.CustomNodeId = 100;
shape.WrapType = WrapType.Inline;
paragraph.AppendChild(shape);

paragraph.AppendChild(new Run(doc, "Hello again!"));

// 遍历段落的直接子元素集合，
// 并打印我们在其中找到的任何运行或形状。
NodeCollection children = paragraph.ChildNodes;

Assert.AreEqual(3, paragraph.ChildNodes.Count);

foreach (Node child in children)
    switch (child.NodeType)
    {
        case NodeType.Run:
            Console.WriteLine("Run contents:");
            Console.WriteLine($"\t\"{child.GetText().Trim()}\"");
            break;
        case NodeType.Shape:
            Shape childShape = (Shape)child;
            Console.WriteLine("Shape:");
            Console.WriteLine($"\t{childShape.ShapeType}, {childShape.Width}x{childShape.Height}");
    }
```

### 也可以看看

* 命名空间 [Aspose.Words](../../aspose.words/)
* 部件 [Aspose.Words](../../)


