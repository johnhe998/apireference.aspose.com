---
title: DocumentVisitor.VisitGlossaryDocumentStart
second_title: Aspose.Words لمراجع .NET API
description: DocumentVisitor طريقة. يتم استدعاؤه عند بدء تعداد مستند مسرد المصطلحات.
type: docs
weight: 250
url: /ar/net/aspose.words/documentvisitor/visitglossarydocumentstart/
---
## DocumentVisitor.VisitGlossaryDocumentStart method

يتم استدعاؤه عند بدء تعداد مستند مسرد المصطلحات.

```csharp
public virtual VisitorAction VisitGlossaryDocumentStart(GlossaryDocument glossary)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| glossary | GlossaryDocument | الكائن الذي تتم زيارته. |

### قيمة الإرجاع

أ[`VisitorAction`](../../visitoraction/) القيمة التي تحدد كيفية متابعة التعداد.

### ملاحظات

ملاحظة: لا تتم زيارة عقدة مستند مسرد المصطلحات وأفرادها عند تنفيذ a زائر عبر a[`Document`](../../document/) . إذا كنت ترغب في تنفيذ "زائر" على مستند قاموس المصطلحات a ، فأنت بحاجة إلى الاتصال[`Accept`](../../../aspose.words.buildingblocks/glossarydocument/accept/) .

### أمثلة

يعرض طرق الوصول إلى الكتل البرمجية الإنشائية في مستند مسرد.

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

    // هناك طرق مختلفة للوصول إلى اللبنات الأساسية.
    // 1 - احصل على اللبنات الأساسية الأولى / الأخيرة في المجموعة:
    Assert.AreEqual("Block 1", glossaryDoc.FirstBuildingBlock.Name);
    Assert.AreEqual("Block 5", glossaryDoc.LastBuildingBlock.Name);

    // 2 - احصل على قالب بناء حسب الفهرس:
    Assert.AreEqual("Block 2", glossaryDoc.BuildingBlocks[1].Name);
    Assert.AreEqual("Block 3", glossaryDoc.BuildingBlocks.ToArray()[2].Name);

    // 3 - احصل على أول قالب إنشائي يطابق معرضًا واسمًا وفئة:
    Assert.AreEqual("Block 4", 
        glossaryDoc.GetBuildingBlock(BuildingBlockGallery.All, "(Empty Category)", "Block 4").Name);

    // سنفعل ذلك باستخدام زائر مخصص ،
    // الذي سيعطي كل BuildingBlock في GlossaryDocument GUID فريدًا
    GlossaryDocVisitor visitor = new GlossaryDocVisitor();
    glossaryDoc.Accept(visitor);

    Console.WriteLine(visitor.GetText());

    // في Microsoft Word ، يمكننا الوصول إلى اللبنات الأساسية عبر "إدراج" - > "أجزاء سريعة" - >. "منظم كتل البناء".
    doc.Save(ArtifactsDir + "BuildingBlocks.GlossaryDocument.dotx"); 
}

/// <summary>
/// يعطي كل كتلة إنشائية في مستند قاموس المصطلحات الذي تمت زيارته GUID فريدًا.
/// يخزن أزواج الكتل البرمجية الإنشائية GUID في قاموس.
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

### أنظر أيضا

* enum [VisitorAction](../../visitoraction/)
* class [GlossaryDocument](../../../aspose.words.buildingblocks/glossarydocument/)
* class [DocumentVisitor](../)
* مساحة الاسم [Aspose.Words](../../documentvisitor/)
* المجسم [Aspose.Words](../../../)


