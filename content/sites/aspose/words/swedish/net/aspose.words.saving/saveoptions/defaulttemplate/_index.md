---
title: SaveOptions.DefaultTemplate
second_title: Aspose.Words för .NET API Referens
description: SaveOptions fast egendom. Hämtar eller ställer in sökvägen till standardmall inklusive filnamn. Standardvärdet för den här egenskapen är tom sträng Empty .
type: docs
weight: 40
url: /sv/net/aspose.words.saving/saveoptions/defaulttemplate/
---
## SaveOptions.DefaultTemplate property

Hämtar eller ställer in sökvägen till standardmall (inklusive filnamn). Standardvärdet för den här egenskapen är **tom sträng** (Empty ).

```csharp
public string DefaultTemplate { get; set; }
```

### Anmärkningar

Om det anges används den här sökvägen för att ladda mallen när[`AutomaticallyUpdateStyles`](../../../aspose.words/document/automaticallyupdatestyles/) är sant, men[`AttachedTemplate`](../../../aspose.words/document/attachedtemplate/) är tom.

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

* class [SaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../saveoptions/)
* hopsättning [Aspose.Words](../../../)


