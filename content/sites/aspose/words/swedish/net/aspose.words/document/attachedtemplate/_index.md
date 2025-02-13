---
title: Document.AttachedTemplate
second_title: Aspose.Words för .NET API Referens
description: Document fast egendom. Hämtar eller ställer in hela sökvägen för mallen som är bifogad till dokumentet.
type: docs
weight: 20
url: /sv/net/aspose.words/document/attachedtemplate/
---
## Document.AttachedTemplate property

Hämtar eller ställer in hela sökvägen för mallen som är bifogad till dokumentet.

```csharp
public string AttachedTemplate { get; set; }
```

### Undantag

| undantag | skick |
| --- | --- |
| ArgumentNullException | Kastar om du försöker ställa in ett nollvärde. |

### Anmärkningar

Tom sträng betyder att dokumentet är bifogat till mallen Normal.

### Exempel

Visar hur man ställer in en standardmall för dokument som inte har bifogade mallar.

```csharp
Document doc = new Document();

// Aktivera automatisk stiluppdatering, men bifoga inte ett malldokument.
doc.AutomaticallyUpdateStyles = true;

Assert.AreEqual(string.Empty, doc.AttachedTemplate);

// Eftersom det inte finns något malldokument hade dokumentet ingenstans att spåra stiländringar.
// Använd ett SaveOptions-objekt för att automatiskt ställa in en mall
// om ett dokument som vi sparar inte har ett.
SaveOptions options = SaveOptions.CreateSaveOptions("Document.DefaultTemplate.docx");
options.DefaultTemplate = MyDir + "Business brochure.dotx";

doc.Save(ArtifactsDir + "Document.DefaultTemplate.docx", options);
```

### Se även

* class [Document](../)
* namnutrymme [Aspose.Words](../../document/)
* hopsättning [Aspose.Words](../../../)


