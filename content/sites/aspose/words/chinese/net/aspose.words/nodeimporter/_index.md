---
title: Class NodeImporter
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.NodeImporter 班级. 允许有效地将节点从一个文档重复导入到另一个文档
type: docs
weight: 3970
url: /zh/net/aspose.words/nodeimporter/
---
## NodeImporter class

允许有效地将节点从一个文档重复导入到另一个文档。

```csharp
public class NodeImporter
```

## 构造函数

| 姓名 | 描述 |
| --- | --- |
| [NodeImporter](nodeimporter/#constructor)(DocumentBase, DocumentBase, ImportFormatMode) | 初始化`NodeImporter`类. |
| [NodeImporter](nodeimporter/#constructor_1)(DocumentBase, DocumentBase, ImportFormatMode, ImportFormatOptions) | 初始化`NodeImporter`类. |

## 方法

| 姓名 | 描述 |
| --- | --- |
| [ImportNode](../../aspose.words/nodeimporter/importnode/)(Node, bool) | 将节点从一个文档导入到另一个文档。 |

### 评论

Aspose.Words 提供了在 Microsoft Word 文档之间轻松复制和移动 Fragments 的功能。这称为“导入节点”。 在将一个文档中的片段插入另一个文档之前，您需要“导入”它。 导入会创建原始节点的深层克隆，准备好插入到 目标文档中。

导入节点最简单的方法是使用[`ImportNode`](../documentbase/importnode/)method 由[`DocumentBase`](../documentbase/)目的。

但是，当您需要多次将节点从一个文档导入到另一个文档时， 最好使用`NodeImporter`班级。这`NodeImporter` 类允许最小化在目标文档中创建的样式和列表的数量。

将片段从一个 Microsoft Word 文档复制或移动到另一个文档给 Aspose.Words 带来了许多技术挑战。在 Word 文档中，样式和列表格式设置 与文档文本分开存储。段落 和文本行仅通过内部唯一标识符引用样式。

挑战来自不同文档中的样式和列表不同这一事实。 例如，要将使用 Heading 1 样式格式化的段落从一个文档复制到另一个文档， 必须考虑许多事情：决定是否将 Heading 1 样式从 源文档复制到目标文档，克隆段落，更新 cloned 段落，使其引用目标文档中正确的 Heading 1 样式。 如果必须复制样式，则它的所有样式引用（基于 style 和下一段样式）应该被分析并且可能被复制等等。 复制项目符号或编号的段落时存在类似的问题，因为 Microsoft Word 将列表定义与文本分开存储。

这`NodeImporter`类就像一个上下文，在导入期间保存“翻译表” 。它在源文档和 目标文档中的样式和列表之间正确转换。

### 例子

演示如何将一个文档的内容插入到另一个文档的书签中。

```csharp
[Test]
public void InsertAtBookmark()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.StartBookmark("InsertionPoint");
    builder.Write("We will insert a document here: ");
    builder.EndBookmark("InsertionPoint");

    Document docToInsert = new Document();
    builder = new DocumentBuilder(docToInsert);

    builder.Write("Hello world!");

    docToInsert.Save(ArtifactsDir + "NodeImporter.InsertAtMergeField.docx");

    Bookmark bookmark = doc.Range.Bookmarks["InsertionPoint"];
    InsertDocument(bookmark.BookmarkStart.ParentNode, docToInsert);

    Assert.AreEqual("We will insert a document here: " +
                    "\rHello world!", doc.GetText().Trim());
}

/// <summary>
/// 在指定节点之后插入文档的内容。
/// </summary>
static void InsertDocument(Node insertionDestination, Document docToInsert)
{
    if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
    {
        CompositeNode destinationParent = insertionDestination.ParentNode;

        NodeImporter importer =
            new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

        // 循环遍历部分主体中的所有块级节点，
        // 然后克隆并插入不是节的最后一个空段落的每个节点。
        foreach (Section srcSection in docToInsert.Sections.OfType<Section>())
            foreach (Node srcNode in srcSection.Body)
            {
                if (srcNode.NodeType == NodeType.Paragraph)
                {
                    Paragraph para = (Paragraph)srcNode;
                    if (para.IsEndOfSection && !para.HasChildNodes)
                        continue;
                }

                Node newNode = importer.ImportNode(srcNode, true);

                destinationParent.InsertAfter(newNode, insertionDestination);
                insertionDestination = newNode;
            }
    }
    else
    {
        throw new ArgumentException("The destination node should be either a paragraph or table.");
    }
}
```

### 也可以看看

* 命名空间 [Aspose.Words](../../aspose.words/)
* 部件 [Aspose.Words](../../)


