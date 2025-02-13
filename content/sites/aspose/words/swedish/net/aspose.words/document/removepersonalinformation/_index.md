---
title: Document.RemovePersonalInformation
second_title: Aspose.Words för .NET API Referens
description: Document fast egendom. Hämtar eller ställer in en flagga som indikerar att Microsoft Word kommer att ta bort all användarinformation från kommentarer revisioner och dokumentegenskaper när dokumentet sparas.
type: docs
weight: 320
url: /sv/net/aspose.words/document/removepersonalinformation/
---
## Document.RemovePersonalInformation property

Hämtar eller ställer in en flagga som indikerar att Microsoft Word kommer att ta bort all användarinformation från kommentarer, revisioner och dokumentegenskaper när dokumentet sparas.

```csharp
public bool RemovePersonalInformation { get; set; }
```

### Exempel

Visar hur man aktiverar borttagning av personlig information under en manuell lagring.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Infoga något innehåll med personlig information.
doc.BuiltInDocumentProperties.Author = "John Doe";
doc.BuiltInDocumentProperties.Company = "Placeholder Inc.";

doc.StartTrackRevisions(doc.BuiltInDocumentProperties.Author, DateTime.Now);
builder.Write("Hello world!");
doc.StopTrackRevisions();

// Den här flaggan motsvarar File -> Alternativ -> Trust Center -> Trust Center-inställningar... ->
// Sekretessalternativ -> "Ta bort personlig information från filegenskaper vid spara" i Microsoft Word.
doc.RemovePersonalInformation = saveWithoutPersonalInfo;

// Det här alternativet kommer inte att träda i kraft under en lagringsoperation som görs med Aspose.Words.
// Personuppgifter kommer att tas bort från vårt dokument med flaggan inställd när vi sparar dem manuellt med Microsoft Word.
doc.Save(ArtifactsDir + "Document.RemovePersonalInformation.docx");
doc = new Document(ArtifactsDir + "Document.RemovePersonalInformation.docx");

Assert.AreEqual(saveWithoutPersonalInfo, doc.RemovePersonalInformation);
Assert.AreEqual("John Doe", doc.BuiltInDocumentProperties.Author);
Assert.AreEqual("Placeholder Inc.", doc.BuiltInDocumentProperties.Company);
Assert.AreEqual("John Doe", doc.Revisions[0].Author);
```

### Se även

* class [Document](../)
* namnutrymme [Aspose.Words](../../document/)
* hopsättning [Aspose.Words](../../../)


