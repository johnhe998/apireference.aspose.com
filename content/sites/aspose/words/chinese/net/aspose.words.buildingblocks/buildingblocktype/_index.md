---
title: Enum BuildingBlockType
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.BuildingBlocks.BuildingBlockType 枚举. 指定构建块类型该类型可能会影响 Microsoft Word 中 building block 的可见性和行为
type: docs
weight: 160
url: /zh/net/aspose.words.buildingblocks/buildingblocktype/
---
## BuildingBlockType enumeration

指定构建块类型。该类型可能会影响 Microsoft Word 中 building block 的可见性和行为。

```csharp
public enum BuildingBlockType
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| None | `0` | 没有为构建块指定类型信息。 |
| AutomaticallyReplaceNameWithContent | `1` | 每当 将其名称输入应用程序时，允许将构建块自动插入到文档中。 |
| StructuredDocumentTagPlaceholderText | `2` | 构建块是结构化文档标记占位符文本。 |
| FormFieldHelpText | `3` | 构建块是表单字段帮助文本。 |
| Normal | `4` | 构建块是一个普通（即常规）词汇表文档条目。 |
| AutoCorrect | `5` | 构建块与拼写和语法工具相关联。 |
| AutoText | `6` | 构建块是自动图文集条目。 |
| All | `7` | 构建块与所有类型相关联。 |
| Default | `0` | 另存为None. |

### 评论

对应于 **ST_DocPartType**输入 OOXML。

### 例子

演示如何将自定义构建块添加到文档。

```csharp
public void CreateAndInsert()
{
    // 文档的词汇表文档存储构建块。
    Document doc = new Document();
    GlossaryDocument glossaryDoc = new GlossaryDocument();
    doc.GlossaryDocument = glossaryDoc;

    // 创建一个构建块，为其命名，然后将其添加到词汇表文档中。
    BuildingBlock block = new BuildingBlock(glossaryDoc)
    {
        Name = "Custom Block"
    };

    glossaryDoc.AppendChild(block);

    // 所有新的构建块 GUID 默认都具有相同的零值，我们可以给它们一个新的唯一值。
    Assert.AreEqual("00000000-0000-0000-0000-000000000000", block.Guid.ToString());

    block.Guid = Guid.NewGuid();

    // 以下属性对构建块进行分类
    // 在菜单中，我们可以通过“插入”在 Microsoft Word 中访问 -> “快速零件”-> “积木组织者”。
    Assert.AreEqual("(Empty Category)", block.Category);
    Assert.AreEqual(BuildingBlockType.None, block.Type);
    Assert.AreEqual(BuildingBlockGallery.All, block.Gallery);
    Assert.AreEqual(BuildingBlockBehavior.Content, block.Behavior);

    // 在我们可以将这个构建块添加到我们的文档之前，我们需要给它一些内容，
    // 我们将使用文档访问者来完成。此访问者还将设置类别、画廊和行为。
    BuildingBlockVisitor visitor = new BuildingBlockVisitor(glossaryDoc);
    block.Accept(visitor);

    // 我们可以访问我们刚刚从词汇表文档中创建的块。
    BuildingBlock customBlock = glossaryDoc.GetBuildingBlock(BuildingBlockGallery.QuickParts,
        "My custom building blocks", "Custom Block");

    // 块本身是包含文本的部分。
    Assert.AreEqual($"Text inside {customBlock.Name}\f", customBlock.FirstSection.Body.FirstParagraph.GetText());
    Assert.AreEqual(customBlock.FirstSection, customBlock.LastSection);

    // 现在，我们可以将它作为一个新部分插入到文档中。
    doc.AppendChild(doc.ImportNode(customBlock.FirstSection, true));

    // 我们也可以在 Microsoft Word 的 Building Blocks Organizer 中找到并手动放置。
    doc.Save(ArtifactsDir + "BuildingBlocks.CreateAndInsert.dotx");
}

/// <summary>
/// 设置一个已访问的构建块作为快速部件插入到文档中，并在其内容中添加文本。
/// </summary>
public class BuildingBlockVisitor : DocumentVisitor
{
    public BuildingBlockVisitor(GlossaryDocument ownerGlossaryDoc)
    {
        mBuilder = new StringBuilder();
        mGlossaryDoc = ownerGlossaryDoc;
    }

    public override VisitorAction VisitBuildingBlockStart(BuildingBlock block)
    {
        // 将 Building Block 配置为快速部件，并添加 Building Blocks Organizer 使用的属性。
        block.Behavior = BuildingBlockBehavior.Paragraph;
        block.Category = "My custom building blocks";
        block.Description =
            "Using this block in the Quick Parts section of word will place its contents at the cursor.";
        block.Gallery = BuildingBlockGallery.QuickParts;

        // 添加一个带文本的部分。
        // 将块插入文档将在该位置附加该部分及其子节点。
        Section section = new Section(mGlossaryDoc);
        block.AppendChild(section);
        block.FirstSection.EnsureMinimum();

        Run run = new Run(mGlossaryDoc, "Text inside " + block.Name);
        block.FirstSection.Body.FirstParagraph.AppendChild(run);

        return VisitorAction.Continue;
    }

    public override VisitorAction VisitBuildingBlockEnd(BuildingBlock block)
    {
        mBuilder.Append("Visited " + block.Name + "\r\n");
        return VisitorAction.Continue;
    }

    private readonly StringBuilder mBuilder;
    private readonly GlossaryDocument mGlossaryDoc;
}
```

### 也可以看看

* 命名空间 [Aspose.Words.BuildingBlocks](../../aspose.words.buildingblocks/)
* 部件 [Aspose.Words](../../)


