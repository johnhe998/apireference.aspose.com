---
title: Inline.IsMoveFromRevision
second_title: Aspose.Words for .NET API 参考
description: Inline 财产. 返回 真的如果启用更改跟踪时此对象在 Microsoft Word 中被移动删除
type: docs
weight: 50
url: /zh/net/aspose.words/inline/ismovefromrevision/
---
## Inline.IsMoveFromRevision property

返回 **真的**如果启用更改跟踪时此对象在 Microsoft Word 中被移动（删除）。

```csharp
public bool IsMoveFromRevision { get; }
```

### 例子

显示如何确定内联节点的修订类型。

```csharp
Document doc = new Document(MyDir + "Revision runs.docx");

// 当我们在编辑文档的同时出现“Track Changes”选项，在via Review ->中找到追踪，
// 在 Microsoft Word 中打开，我们应用的更改算作修订。
// 使用 Aspose.Words 编辑文档时，我们可以通过以下方式开始跟踪修订
// 调用文档的“StartTrackRevisions”方法并使用“StopTrackRevisions”方法停止跟踪。
// 我们可以接受修订以将它们吸收到文档中
// 或拒绝它们以有效地更改提议的更改。
Assert.AreEqual(6, doc.Revisions.Count);

// 修订的父节点是修订所关注的运行。运行是一个内联节点。
Run run = (Run)doc.Revisions[0].ParentNode;

Paragraph firstParagraph = run.ParentParagraph;
RunCollection runs = firstParagraph.Runs;

Assert.AreEqual(6, runs.ToArray().Length);

// 以下是可以标记内联节点的五种类型的修订。
// 1 - “插入”修订：
// 当我们在跟踪更改时插入文本时会发生此修订。
Assert.IsTrue(runs[2].IsInsertRevision);

// 2 - “格式”修订：
// 当我们在跟踪更改时更改文本格式时会发生此修订。
Assert.IsTrue(runs[2].IsFormatRevision);

// 3 - “移动”版本：
// 当我们在 Microsoft Word 中突出显示文本，然后将其拖到文档中的不同位置时
// 在跟踪更改时，会出现两个修订。
// “移动”版本是我们移动之前文本的副本。
Assert.IsTrue(runs[4].IsMoveFromRevision);

// 4 - “移至”修订版：
// “移动到”修订版是我们在文档中移动到其新位置的文本。
// 对于我们执行的每个移动修订，“从”和“移动到”修订成对出现。
// 接受移动修订删除“移动”修订及其文本，
// 并保留“移至”修订版中的文本。
// 拒绝移动修订相反地保留“移动”修订并删除“移动到”修订。
Assert.IsTrue(runs[1].IsMoveToRevision);

// 5 - “删除”修订：
// 当我们在跟踪更改时删除文本时会发生此修订。当我们删除这样的文本时，
// 它将作为修订保留在文档中，直到我们接受修订，
// 这将永久删除文本，或者拒绝修订，这将使我们删除的文本保持在原来的位置。
Assert.IsTrue(runs[5].IsDeleteRevision);
```

### 也可以看看

* class [Inline](../)
* 命名空间 [Aspose.Words](../../inline/)
* 部件 [Aspose.Words](../../../)


