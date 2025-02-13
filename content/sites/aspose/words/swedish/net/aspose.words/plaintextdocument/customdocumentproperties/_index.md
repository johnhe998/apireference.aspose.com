---
title: PlainTextDocument.CustomDocumentProperties
second_title: Aspose.Words för .NET API Referens
description: PlainTextDocument fast egendom. BlirCustomDocumentProperties av dokumentet.
type: docs
weight: 30
url: /sv/net/aspose.words/plaintextdocument/customdocumentproperties/
---
## PlainTextDocument.CustomDocumentProperties property

Blir`CustomDocumentProperties` av dokumentet.

```csharp
public CustomDocumentProperties CustomDocumentProperties { get; }
```

### Exempel

Visar hur du laddar innehållet i ett Microsoft Word-dokument i klartext och sedan kommer åt originaldokumentets anpassade egenskaper.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");
doc.CustomDocumentProperties.Add("Location of writing", "123 Main St, London, UK");

doc.Save(ArtifactsDir + "PlainTextDocument.CustomDocumentProperties.docx");

PlainTextDocument plaintext = new PlainTextDocument(ArtifactsDir + "PlainTextDocument.CustomDocumentProperties.docx");

Assert.AreEqual("Hello world!", plaintext.Text.Trim());
Assert.AreEqual("123 Main St, London, UK", plaintext.CustomDocumentProperties["Location of writing"].Value);
```

### Se även

* class [CustomDocumentProperties](../../../aspose.words.properties/customdocumentproperties/)
* class [PlainTextDocument](../)
* namnutrymme [Aspose.Words](../../plaintextdocument/)
* hopsättning [Aspose.Words](../../../)


