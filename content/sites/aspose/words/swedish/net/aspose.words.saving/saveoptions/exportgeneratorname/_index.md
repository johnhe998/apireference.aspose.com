---
title: SaveOptions.ExportGeneratorName
second_title: Aspose.Words för .NET API Referens
description: SaveOptions fast egendom. När sant gör att namnet och versionen av Aspose.Words bäddas in i producerade filer. Standardvärdet är Sann .
type: docs
weight: 80
url: /sv/net/aspose.words.saving/saveoptions/exportgeneratorname/
---
## SaveOptions.ExportGeneratorName property

När sant, gör att namnet och versionen av Aspose.Words bäddas in i producerade filer. Standardvärdet är **Sann** .

```csharp
public bool ExportGeneratorName { get; set; }
```

### Exempel

Visar hur man inaktiverar att lägga till namn och version av Aspose.Words i producerade filer.

```csharp
Document doc = new Document();

// Använd https://docs.aspose.com/words/net/generator-or-producer-name-included-in-output-documents/ för att veta hur man kontrollerar resultatet.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { ExportGeneratorName = false };

doc.Save(ArtifactsDir + "OoxmlSaveOptions.ExportGeneratorName.docx", saveOptions);
```

### Se även

* class [SaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../saveoptions/)
* hopsättning [Aspose.Words](../../../)


