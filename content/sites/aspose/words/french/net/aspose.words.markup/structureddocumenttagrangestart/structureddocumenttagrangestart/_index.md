---
title: StructuredDocumentTagRangeStart.StructuredDocumentTagRangeStart
second_title: Référence de l'API Aspose.Words pour .NET
description: StructuredDocumentTagRangeStart constructeur. Initialise une nouvelle instance du Début de plage de balises de document structuré classe.
type: docs
weight: 10
url: /fr/net/aspose.words.markup/structureddocumenttagrangestart/structureddocumenttagrangestart/
---
## StructuredDocumentTagRangeStart constructor

Initialise une nouvelle instance du **Début de plage de balises de document structuré** classe.

```csharp
public StructuredDocumentTagRangeStart(DocumentBase doc, SdtType type)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| doc | DocumentBase | Le document du propriétaire. |
| type | SdtType | Type de nœud SDT. |

### Remarques

Les types de SDT suivants peuvent être créés :

* Checkbox
* DropDownList
* ComboBox
* Date
* BuildingBlockGallery
* Group
* Picture
* RichText
* PlainText

### Exemples

Montre comment créer/supprimer une balise de document structuré et son contenu.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Writeln("StructuredDocumentTag element");

    InsertStructuredDocumentTagRanges(doc, out StructuredDocumentTagRangeStart rangeStart);

    // Supprime la balise de document structuré à distance, mais conserve le contenu à l'intérieur.
    rangeStart.RemoveSelfOnly();

    rangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(
        NodeType.StructuredDocumentTagRangeStart, 0, false);
    Assert.AreEqual(null, rangeStart);

    StructuredDocumentTagRangeEnd rangeEnd = (StructuredDocumentTagRangeEnd)doc.GetChild(
        NodeType.StructuredDocumentTagRangeEnd, 0, false);

    Assert.AreEqual(null, rangeEnd);
    Assert.AreEqual("StructuredDocumentTag element", doc.GetText().Trim());

    InsertStructuredDocumentTagRanges(doc, out rangeStart);

    Node paragraphNode = rangeStart.LastOrDefault();
    Assert.AreEqual("StructuredDocumentTag element", paragraphNode?.GetText().Trim());

    // Supprime la balise de document structuré à distance et le contenu à l'intérieur.
    rangeStart.RemoveAllChildren();

    paragraphNode = rangeStart.LastOrDefault();
    Assert.AreEqual(null, paragraphNode?.GetText());
}

public void InsertStructuredDocumentTagRanges(Document doc, out StructuredDocumentTagRangeStart rangeStart)
{
    rangeStart = new StructuredDocumentTagRangeStart(doc, SdtType.PlainText);
    StructuredDocumentTagRangeEnd rangeEnd = new StructuredDocumentTagRangeEnd(doc, rangeStart.Id);

    doc.FirstSection.Body.InsertBefore(rangeStart, doc.FirstSection.Body.FirstParagraph);
    doc.LastSection.Body.InsertAfter(rangeEnd, doc.FirstSection.Body.FirstParagraph);
}
```

### Voir également

* class [DocumentBase](../../../aspose.words/documentbase/)
* enum [SdtType](../../sdttype/)
* class [StructuredDocumentTagRangeStart](../)
* espace de noms [Aspose.Words.Markup](../../structureddocumenttagrangestart/)
* Assemblée [Aspose.Words](../../../)


