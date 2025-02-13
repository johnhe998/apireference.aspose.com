---
title: StructuredDocumentTag.PlaceholderName
second_title: Aspose.Words för .NET API Referens
description: StructuredDocumentTag fast egendom. Hämtar eller sätter Namn påBuildingBlock som innehåller platshållartext.
type: docs
weight: 240
url: /sv/net/aspose.words.markup/structureddocumenttag/placeholdername/
---
## StructuredDocumentTag.PlaceholderName property

Hämtar eller sätter Namn på[`BuildingBlock`](../../../aspose.words.buildingblocks/buildingblock/) som innehåller platshållartext.

Byggblock med detta namn[`Name`](../../../aspose.words.buildingblocks/buildingblock/name/) måste vara närvarande i[`GlossaryDocument`](../../../aspose.words/document/glossarydocument/) annarsInvalidOperationException kommer att inträffa.

```csharp
public string PlaceholderName { get; set; }
```

### Exempel

Visar hur man använder ett byggblocks innehåll som en anpassad platshållartext för en strukturerad dokumenttagg.

```csharp
Document doc = new Document();

// Infoga en textstrukturerad dokumenttagg av typen "PlainText", som kommer att fungera som en textruta.
// Innehållet som det kommer att visa som standard är ett "Klicka här för att skriva in text." prompt.
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Inline);

// Vi kan få taggen att visa innehållet i ett byggblock istället för standardtexten.
// Lägg först till ett byggblock med innehåll i ordlistans dokument.
GlossaryDocument glossaryDoc = doc.GlossaryDocument;

BuildingBlock substituteBlock = new BuildingBlock(glossaryDoc);
substituteBlock.Name = "Custom Placeholder";
substituteBlock.AppendChild(new Section(glossaryDoc));
substituteBlock.FirstSection.AppendChild(new Body(glossaryDoc));
substituteBlock.FirstSection.Body.AppendParagraph("Custom placeholder text.");

glossaryDoc.AppendChild(substituteBlock);

// Använd sedan den strukturerade dokumenttaggens "PlaceholderName"-egenskap för att referera till den byggstenen med namn.
tag.PlaceholderName = "Custom Placeholder";

// Om "PlaceholderName" hänvisar till ett befintligt block i det överordnade dokumentets ordlista,
// vi kommer att kunna verifiera byggstenen via egenskapen "Placeholder".
Assert.AreEqual(substituteBlock, tag.Placeholder);

// Ställ in egenskapen "IsShowingPlaceholderText" till "true" för att behandla
// strukturerad dokumenttaggs nuvarande innehåll som platshållartext.
// Detta betyder att om du klickar på textrutan i Microsoft Word kommer alla taggens innehåll omedelbart att markeras.
// Ställ in egenskapen "IsShowingPlaceholderText" till "false" för att få
// strukturerad dokumenttagg för att behandla dess innehåll som text som en användare redan har skrivit in.
// Om du klickar på den här texten i Microsoft Word placeras den blinkande markören på den plats som du klickar på.
tag.IsShowingPlaceholderText = isShowingPlaceholderText;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(tag);

doc.Save(ArtifactsDir + "StructuredDocumentTag.PlaceholderBuildingBlock.docx");
```

### Se även

* class [StructuredDocumentTag](../)
* namnutrymme [Aspose.Words.Markup](../../structureddocumenttag/)
* hopsättning [Aspose.Words](../../../)


