---
title: Enum BuildingBlockBehavior
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.BuildingBlocks.BuildingBlockBehavior uppräkning. Anger beteendet som ska tillämpas på innehållet i byggblocket när det infogas i huvuddokumentet.
type: docs
weight: 130
url: /sv/net/aspose.words.buildingblocks/buildingblockbehavior/
---
## BuildingBlockBehavior enumeration

Anger beteendet som ska tillämpas på innehållet i byggblocket när det infogas i huvuddokumentet.

```csharp
public enum BuildingBlockBehavior
```

### Värderingar

| namn | Värde | Beskrivning |
| --- | --- | --- |
| Content | `0` | Anger att byggstenen ska infogas som inline-innehåll. |
| Paragraph | `1` | Anger att byggstenen ska infogas i sitt eget stycke. |
| Page | `2` | Anger att byggblocket ska läggas till på sin egen sida. |
| Default | `0` | Samma somContent . |

### Anmärkningar

Motsvarar **ST_DocPartBehavior** skriv in OOXML.

### Exempel

Visar hur man lägger till ett anpassat byggblock till ett dokument.

```csharp
public void CreateAndInsert()
{
    // Ett dokuments ordlista dokument lagrar byggstenar.
    Document doc = new Document();
    GlossaryDocument glossaryDoc = new GlossaryDocument();
    doc.GlossaryDocument = glossaryDoc;

    // Skapa ett byggblock, namnge det och lägg sedan till det i ordlistans dokument.
    BuildingBlock block = new BuildingBlock(glossaryDoc)
    {
        Name = "Custom Block"
    };

    glossaryDoc.AppendChild(block);

    // Alla nya byggblock GUID har samma nollvärde som standard, och vi kan ge dem ett nytt unikt värde.
    Assert.AreEqual("00000000-0000-0000-0000-000000000000", block.Guid.ToString());

    block.Guid = Guid.NewGuid();

    // Följande egenskaper kategoriserar byggstenar
    // i menyn kan vi komma åt i Microsoft Word via "Infoga" -> "Snabbdelar" -> "Byggstensarrangör".
    Assert.AreEqual("(Empty Category)", block.Category);
    Assert.AreEqual(BuildingBlockType.None, block.Type);
    Assert.AreEqual(BuildingBlockGallery.All, block.Gallery);
    Assert.AreEqual(BuildingBlockBehavior.Content, block.Behavior);

    // Innan vi kan lägga till den här byggstenen i vårt dokument måste vi ge det lite innehåll,
    // vilket vi kommer att göra med en dokumentbesökare. Den här besökaren kommer också att ange en kategori, ett galleri och ett beteende.
    BuildingBlockVisitor visitor = new BuildingBlockVisitor(glossaryDoc);
    block.Accept(visitor);

    // Vi kan komma åt blocket som vi just skapade från ordlistans dokument.
    BuildingBlock customBlock = glossaryDoc.GetBuildingBlock(BuildingBlockGallery.QuickParts,
        "My custom building blocks", "Custom Block");

    // Själva blocket är ett avsnitt som innehåller texten.
    Assert.AreEqual($"Text inside {customBlock.Name}\f", customBlock.FirstSection.Body.FirstParagraph.GetText());
    Assert.AreEqual(customBlock.FirstSection, customBlock.LastSection);

    // Nu kan vi infoga det i dokumentet som ett nytt avsnitt.
    doc.AppendChild(doc.ImportNode(customBlock.FirstSection, true));

    // Vi kan också hitta det i Microsoft Words Building Blocks Organizer och placera det manuellt.
    doc.Save(ArtifactsDir + "BuildingBlocks.CreateAndInsert.dotx");
}

/// <summary>
/// Konfigurerar ett besökt byggblock som ska infogas i dokumentet som en snabb del och lägger till text i dess innehåll.
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
        // Konfigurera byggblocket som en snabbdel och lägg till egenskaper som används av Building Blocks Organizer.
        block.Behavior = BuildingBlockBehavior.Paragraph;
        block.Category = "My custom building blocks";
        block.Description =
            "Using this block in the Quick Parts section of word will place its contents at the cursor.";
        block.Gallery = BuildingBlockGallery.QuickParts;

        // Lägg till ett avsnitt med text.
        // Om du infogar blocket i dokumentet kommer detta avsnitt att läggas till med dess underordnade noder på platsen.
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

### Se även

* namnutrymme [Aspose.Words.BuildingBlocks](../../aspose.words.buildingblocks/)
* hopsättning [Aspose.Words](../../)


