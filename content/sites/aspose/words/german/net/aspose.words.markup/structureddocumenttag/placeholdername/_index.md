---
title: StructuredDocumentTag.PlaceholderName
second_title: Aspose.Words für .NET-API-Referenz
description: StructuredDocumentTag eigendom. Ruft den Namen der ab oder legt ihn festBuildingBlock mit Platzhaltertext.
type: docs
weight: 240
url: /de/net/aspose.words.markup/structureddocumenttag/placeholdername/
---
## StructuredDocumentTag.PlaceholderName property

Ruft den Namen der ab oder legt ihn fest[`BuildingBlock`](../../../aspose.words.buildingblocks/buildingblock/) mit Platzhaltertext.

Baustein mit diesem Namen[`Name`](../../../aspose.words.buildingblocks/buildingblock/name/) muss dabei sein[`GlossaryDocument`](../../../aspose.words/document/glossarydocument/) ansonstenInvalidOperationException wird passieren.

```csharp
public string PlaceholderName { get; set; }
```

### Beispiele

Zeigt, wie der Inhalt eines Bausteins als benutzerdefinierter Platzhaltertext für ein strukturiertes Dokument-Tag verwendet wird.

```csharp
Document doc = new Document();

// Fügen Sie ein strukturiertes Klartext-Dokument-Tag des Typs "PlainText" ein, das als Textfeld fungiert.
// Der Inhalt, der standardmäßig angezeigt wird, ist "Klicken Sie hier, um Text einzugeben." prompt.
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Inline);

// Wir können das Tag dazu bringen, den Inhalt eines Bausteins anstelle des Standardtexts anzuzeigen.
// Zuerst einen Baustein mit Inhalt zum Glossardokument hinzufügen.
GlossaryDocument glossaryDoc = doc.GlossaryDocument;

BuildingBlock substituteBlock = new BuildingBlock(glossaryDoc);
substituteBlock.Name = "Custom Placeholder";
substituteBlock.AppendChild(new Section(glossaryDoc));
substituteBlock.FirstSection.AppendChild(new Body(glossaryDoc));
substituteBlock.FirstSection.Body.AppendParagraph("Custom placeholder text.");

glossaryDoc.AppendChild(substituteBlock);

// Verwenden Sie dann die Eigenschaft „PlaceholderName“ des strukturierten Dokument-Tags, um diesen Baustein namentlich zu referenzieren.
tag.PlaceholderName = "Custom Placeholder";

// Wenn "PlaceholderName" auf einen vorhandenen Block im Glossardokument des übergeordneten Dokuments verweist,
// Wir können den Baustein über die Eigenschaft "Platzhalter" überprüfen.
Assert.AreEqual(substituteBlock, tag.Placeholder);

// Setzen Sie die Eigenschaft "IsShowingPlaceholderText" auf "true", um die zu behandeln
// Aktueller Inhalt des strukturierten Dokument-Tags als Platzhaltertext.
// Das bedeutet, dass beim Klicken auf das Textfeld in Microsoft Word sofort der gesamte Inhalt des Tags hervorgehoben wird.
// Setzen Sie die Eigenschaft "IsShowingPlaceholderText" auf "false", um die zu erhalten
// strukturiertes Dokument-Tag, um seinen Inhalt als Text zu behandeln, den ein Benutzer bereits eingegeben hat.
// Wenn Sie in Microsoft Word auf diesen Text klicken, wird der blinkende Cursor an der angeklickten Stelle platziert.
tag.IsShowingPlaceholderText = isShowingPlaceholderText;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(tag);

doc.Save(ArtifactsDir + "StructuredDocumentTag.PlaceholderBuildingBlock.docx");
```

### Siehe auch

* class [StructuredDocumentTag](../)
* namensraum [Aspose.Words.Markup](../../structureddocumenttag/)
* Montage [Aspose.Words](../../../)


