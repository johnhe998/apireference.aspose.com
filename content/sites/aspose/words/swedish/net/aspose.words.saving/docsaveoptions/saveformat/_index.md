---
title: DocSaveOptions.SaveFormat
second_title: Aspose.Words för .NET API Referens
description: DocSaveOptions fast egendom. Anger formatet som dokumentet kommer att sparas i om detta sparaalternativobjekt används. Kan varaDoc ellerDot .
type: docs
weight: 40
url: /sv/net/aspose.words.saving/docsaveoptions/saveformat/
---
## DocSaveOptions.SaveFormat property

Anger formatet som dokumentet kommer att sparas i om detta sparaalternativ-objekt används. Kan varaDoc ellerDot .

```csharp
public override SaveFormat SaveFormat { get; set; }
```

### Exempel

Visar hur du ställer in sparalternativ för äldre Microsoft Word-format.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Hello world!");

DocSaveOptions options = new DocSaveOptions(SaveFormat.Doc);

// Ställ in ett lösenord som skyddar laddningen av dokumentet med Microsoft Word eller Aspose.Words.
// Observera att detta inte krypterar innehållet i dokumentet på något sätt.
options.Password = "MyPassword";

// Om dokumentet innehåller en routingsedel kan vi bevara den medan vi sparar genom att sätta denna flagga till true.
options.SaveRoutingSlip = true;

doc.Save(ArtifactsDir + "DocSaveOptions.SaveAsDoc.doc", options);

// För att kunna ladda dokumentet,
// vi kommer att behöva använda lösenordet vi angav i DocSaveOptions-objektet i ett LoadOptions-objekt.
Assert.Throws<IncorrectPasswordException>(() => doc = new Document(ArtifactsDir + "DocSaveOptions.SaveAsDoc.doc"));

LoadOptions loadOptions = new LoadOptions("MyPassword");
doc = new Document(ArtifactsDir + "DocSaveOptions.SaveAsDoc.doc", loadOptions);

Assert.AreEqual("Hello world!", doc.GetText().Trim());
```

### Se även

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [DocSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../docsaveoptions/)
* hopsättning [Aspose.Words](../../../)


