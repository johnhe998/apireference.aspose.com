---
title: StructuredDocumentTag.WordOpenXML
second_title: Référence de l'API Aspose.Words pour .NET
description: StructuredDocumentTag propriété. Obtient une chaîne qui représente le XML contenu dans le nœud duFlatOpc format.
type: docs
weight: 300
url: /fr/net/aspose.words.markup/structureddocumenttag/wordopenxml/
---
## StructuredDocumentTag.WordOpenXML property

Obtient une chaîne qui représente le XML contenu dans le nœud duFlatOpc format.

```csharp
public string WordOpenXML { get; }
```

### Exemples

Montre comment obtenir le XML contenu dans le nœud au format FlatOpc.

```csharp
Document doc = new Document(MyDir + "Structured document tags.docx");

List<StructuredDocumentTag> tags = doc.GetChildNodes(NodeType.StructuredDocumentTag, true)
    .OfType<StructuredDocumentTag>().ToList();

Assert.True(tags[0].WordOpenXML
    .Contains(
        "<pkg:part pkg:name=\"/docProps/app.xml\" pkg:contentType=\"application/vnd.openxmlformats-officedocument.extended-properties+xml\">"));
```

### Voir également

* class [StructuredDocumentTag](../)
* espace de noms [Aspose.Words.Markup](../../structureddocumenttag/)
* Assemblée [Aspose.Words](../../../)


