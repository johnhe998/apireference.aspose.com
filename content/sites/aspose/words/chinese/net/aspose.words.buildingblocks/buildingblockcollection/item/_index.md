---
title: BuildingBlockCollection.Item
second_title: Aspose.Words for .NET API 参考
description: BuildingBlockCollection 财产. 在给定索引处检索构建块
type: docs
weight: 10
url: /zh/net/aspose.words.buildingblocks/buildingblockcollection/item/
---
## BuildingBlockCollection indexer

在给定索引处检索构建块。

```csharp
public BuildingBlock this[int index] { get; }
```

| 范围 | 描述 |
| --- | --- |
| index | 构建块列表的索引。 |

### 评论

该索引从零开始。

允许使用负索引并指示从集合的背面进行访问。 例如 -1 表示最后一项，-2 表示倒数第二个，依此类推。

如果 index 大于或等于列表中的项目数，则返回空引用。

如果 index 为负且其绝对值大于列表中的项目数，则返回空引用。

### 例子

显示访问词汇表文档中构建块的方法。

```csharp
public void GlossaryDocument()
{
    Document doc = new Document();
    GlossaryDocument glossaryDoc = new GlossaryDocument();

    glossaryDoc.AppendChild(new BuildingBlock(glossaryDoc) { Name = "Block 1" });
    glossaryDoc.AppendChild(new BuildingBlock(glossaryDoc) { Name = "Block 2" });
    glossaryDoc.AppendChild(new BuildingBlock(glossaryDoc) { Name = "Block 3" });
    glossaryDoc.AppendChild(new BuildingBlock(glossaryDoc) { Name = "Block 4" });
    glossaryDoc.AppendChild(new BuildingBlock(glossaryDoc) { Name = "Block 5" });

    Assert.AreEqual(5, glossaryDoc.BuildingBlocks.Count);

    doc.GlossaryDocument = glossaryDoc;

    // 有多种访问构建块的方法。
    // 1 - 获取集合中的第一个/最后一个构建块：
    Assert.AreEqual("Block 1", glossaryDoc.FirstBuildingBlock.Name);
    Assert.AreEqual("Block 5", glossaryDoc.LastBuildingBlock.Name);

    // 2 - 通过索引获取构建块：
    Assert.AreEqual("Block 2", glossaryDoc.BuildingBlocks[1].Name);
    Assert.AreEqual("Block 3", glossaryDoc.BuildingBlocks.ToArray()[2].Name);

    // 3 - 获取与画廊、名称和类别匹配的第一个构建块：
    Assert.AreEqual("Block 4", 
        glossaryDoc.GetBuildingBlock(BuildingBlockGallery.All, "(Empty Category)", "Block 4").Name);

    // 我们将使用自定义访问者来做到这一点，
    // 这将为 GlossaryDocument 中的每个 BuildingBlock 提供唯一的 GUID
    GlossaryDocVisitor visitor = new GlossaryDocVisitor();
    glossaryDoc.Accept(visitor);

    Console.WriteLine(visitor.GetText());

    // 在 Microsoft Word 中，我们可以通过“插入”-> 访问构建块“快速零件”-> “积木组织者”。
    doc.Save(ArtifactsDir + "BuildingBlocks.GlossaryDocument.dotx"); 
}

/// <summary>
/// 为访问的词汇表文档中的每个构建块提供唯一的 GUID。
/// 将 GUID 构建块对存储在字典中。
/// </summary>
public class GlossaryDocVisitor : DocumentVisitor
{
    public GlossaryDocVisitor()
    {
        mBlocksByGuid = new Dictionary<Guid, BuildingBlock>();
        mBuilder = new StringBuilder();
    }

    public string GetText()
    {
        return mBuilder.ToString();
    }

    public Dictionary<Guid, BuildingBlock> GetDictionary()
    {
        return mBlocksByGuid;
    }

    public override VisitorAction VisitGlossaryDocumentStart(GlossaryDocument glossary)
    {
        mBuilder.AppendLine("Glossary document found!");
        return VisitorAction.Continue;
    }

    public override VisitorAction VisitGlossaryDocumentEnd(GlossaryDocument glossary)
    {
        mBuilder.AppendLine("Reached end of glossary!");
        mBuilder.AppendLine("BuildingBlocks found: " + mBlocksByGuid.Count);
        return VisitorAction.Continue;
    }

    public override VisitorAction VisitBuildingBlockStart(BuildingBlock block)
    {
        block.Guid = Guid.NewGuid();
        mBlocksByGuid.Add(block.Guid, block);
        return VisitorAction.Continue;
    }

    public override VisitorAction VisitBuildingBlockEnd(BuildingBlock block)
    {
        mBuilder.AppendLine("\tVisited block \"" + block.Name + "\"");
        mBuilder.AppendLine("\t Type: " + block.Type);
        mBuilder.AppendLine("\t Gallery: " + block.Gallery);
        mBuilder.AppendLine("\t Behavior: " + block.Behavior);
        mBuilder.AppendLine("\t Description: " + block.Description);

        return VisitorAction.Continue;
    }

    private readonly Dictionary<Guid, BuildingBlock> mBlocksByGuid;
    private readonly StringBuilder mBuilder;
}
```

### 也可以看看

* class [BuildingBlock](../../buildingblock/)
* class [BuildingBlockCollection](../)
* 命名空间 [Aspose.Words.BuildingBlocks](../../buildingblockcollection/)
* 部件 [Aspose.Words](../../../)


