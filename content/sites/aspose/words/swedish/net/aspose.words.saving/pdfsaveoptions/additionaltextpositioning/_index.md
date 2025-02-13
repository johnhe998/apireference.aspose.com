---
title: PdfSaveOptions.AdditionalTextPositioning
second_title: Aspose.Words för .NET API Referens
description: PdfSaveOptions fast egendom. En flagga som anger om ytterligare textpositioneringsoperatorer ska skrivas eller inte.
type: docs
weight: 20
url: /sv/net/aspose.words.saving/pdfsaveoptions/additionaltextpositioning/
---
## PdfSaveOptions.AdditionalTextPositioning property

En flagga som anger om ytterligare textpositioneringsoperatorer ska skrivas eller inte.

```csharp
public bool AdditionalTextPositioning { get; set; }
```

### Anmärkningar

Om`Sann` , ytterligare textpositioneringsoperatorer skrivs till utdata-PDF-filen. Detta kan hjälpa till att övervinna problem med felaktig textpositionering på vissa skrivare. Nackdelen är den ökade PDF-dokumentstorleken.

Standardvärdet är`falsk`.

### Exempel

Visa hur man skriver ytterligare textpositioneringsoperatorer.

```csharp
Document doc = new Document(MyDir + "Text positioning operators.docx");

// Skapa ett "PdfSaveOptions"-objekt som vi kan skicka till dokumentets "Spara"-metod
// för att ändra hur den metoden konverterar dokumentet till .PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    TextCompression = PdfTextCompression.None,

    // Ställ in egenskapen "AdditionalTextPositioning" till "true" för att försöka fixa felaktiga
    // elementpositionering i utdata-PDF-filen, om det skulle finnas någon, till priset av ökad filstorlek.
    // Ställ in egenskapen "AdditionalTextPositioning" till "false" för att återge dokumentet som vanligt.
    AdditionalTextPositioning = applyAdditionalTextPositioning
};

doc.Save(ArtifactsDir + "PdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);
```

### Se även

* class [PdfSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../pdfsaveoptions/)
* hopsättning [Aspose.Words](../../../)


