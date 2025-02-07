---
title: PdfSaveOptions.PreserveFormFields
second_title: Aspose.Words för .NET API Referens
description: PdfSaveOptions fast egendom. Anger om Microsoft Wordformulärfält ska bevaras som formulärfält i PDF eller konvertera dem till text. Standard ärfalsk .
type: docs
weight: 240
url: /sv/net/aspose.words.saving/pdfsaveoptions/preserveformfields/
---
## PdfSaveOptions.PreserveFormFields property

Anger om Microsoft Word-formulärfält ska bevaras som formulärfält i PDF eller konvertera dem till text. Standard är`falsk` .

```csharp
public bool PreserveFormFields { get; set; }
```

### Anmärkningar

Microsoft Word-formulärfält inkluderar textinmatning, rullgardinsmeny och kryssrutor.

När inställd på`falsk` , kommer dessa fält att exporteras som text till PDF. När inställd på`Sann`, dessa fält kommer att exporteras som PDF-formulärfält.

När du exporterar formulärfält till PDF som formulärfält kan en viss formateringsförlust uppstå eftersom PDF form -fält inte stöder alla funktioner i Microsoft Word-formulärfält.

Utdatastorleken beror också på innehållsstorleken eftersom redigerbara formulär i Microsoft Word är inline-objekt.

Redigerbara formulär är förbjudna av PDF/A-kompatibilitet.`falsk` värde kommer att användas automatiskt när du sparar till PDF/A.

Formulärfält stöds inte när du sparar till PDF/UA.`falsk` värdet kommer att användas automatiskt.

### Exempel

Visar hur man sparar ett dokument i PDF-format med hjälp av metoden Spara och klassen PdfSaveOptions.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Please select a fruit: ");

// Infoga en kombinationsruta som låter en användare välja ett alternativ från en samling strängar.
builder.InsertComboBox("MyComboBox", new[] { "Apple", "Banana", "Cherry" }, 0);

// Skapa ett "PdfSaveOptions"-objekt som vi kan skicka till dokumentets "Spara"-metod
// för att ändra hur den metoden konverterar dokumentet till .PDF.
PdfSaveOptions pdfOptions = new PdfSaveOptions();

// Ställ in egenskapen "PreserveFormFields" till "true" för att spara formulärfält som interaktiva objekt i utdata-PDF.
// Ställ in egenskapen "PreserveFormFields" till "false" för att frysa alla formulärfält i dokumentet på
// deras nuvarande värden och visa dem som vanlig text i utdata-PDF.
pdfOptions.PreserveFormFields = preserveFormFields;

doc.Save(ArtifactsDir + "PdfSaveOptions.PreserveFormFields.pdf", pdfOptions);
```

### Se även

* class [PdfSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../pdfsaveoptions/)
* hopsättning [Aspose.Words](../../../)


