---
title: StructuredDocumentTag.Style
second_title: Référence de l'API Aspose.Words pour .NET
description: StructuredDocumentTag propriété. Obtient ou définit le style de la balise de document structuré.
type: docs
weight: 260
url: /fr/net/aspose.words.markup/structureddocumenttag/style/
---
## StructuredDocumentTag.Style property

Obtient ou définit le style de la balise de document structuré.

```csharp
public Style Style { get; set; }
```

### Remarques

uniquementCharacter style ouParagraph style avec style de caractère lié peut être défini.

### Exemples

Montre comment utiliser les styles pour les éléments de contrôle de contenu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Vous trouverez ci-dessous deux manières d'appliquer un style du document à une balise de document structuré.
// 1 - Appliquez un objet de style à partir de la collection de styles du document :
Style quoteStyle = doc.Styles[StyleIdentifier.Quote];
StructuredDocumentTag sdtPlainText =
    new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Inline) { Style = quoteStyle };

// 2 - Référencez un style dans le document par son nom :
StructuredDocumentTag sdtRichText =
    new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Inline) { StyleName = "Quote" };

builder.InsertNode(sdtPlainText);
builder.InsertNode(sdtRichText);

Assert.AreEqual(NodeType.StructuredDocumentTag, sdtPlainText.NodeType);

NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTag, true);

foreach (Node node in tags)
{
    StructuredDocumentTag sdt = (StructuredDocumentTag)node;

    Assert.AreEqual(StyleIdentifier.Quote, sdt.Style.StyleIdentifier);
    Assert.AreEqual("Quote", sdt.StyleName);
}
```

### Voir également

* class [Style](../../../aspose.words/style/)
* class [StructuredDocumentTag](../)
* espace de noms [Aspose.Words.Markup](../../structureddocumenttag/)
* Assemblée [Aspose.Words](../../../)


