---
title: StructuredDocumentTag.IsShowingPlaceholderText
second_title: Aspose.Words för .NET API Referens
description: StructuredDocumentTag fast egendom. Anger om innehållet i detta SDT ska tolkas att innehålla platshållare text i motsats till vanligt textinnehåll inom SDT.
type: docs
weight: 150
url: /sv/net/aspose.words.markup/structureddocumenttag/isshowingplaceholdertext/
---
## StructuredDocumentTag.IsShowingPlaceholderText property

Anger om innehållet i detta **SDT** ska tolkas att innehålla platshållare text (i motsats till vanligt textinnehåll inom SDT).

om satt till sant, ska detta tillstånd återupptas (visar platshållartext) när det här dokumentet öppnas.

```csharp
public bool IsShowingPlaceholderText { get; set; }
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


