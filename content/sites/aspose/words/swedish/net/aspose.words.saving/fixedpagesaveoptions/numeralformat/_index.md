---
title: FixedPageSaveOptions.NumeralFormat
second_title: Aspose.Words för .NET API Referens
description: FixedPageSaveOptions fast egendom. Hämtar eller sätterNumeralFormat används för återgivning av siffror. Europeiska siffror används som standard.
type: docs
weight: 40
url: /sv/net/aspose.words.saving/fixedpagesaveoptions/numeralformat/
---
## FixedPageSaveOptions.NumeralFormat property

Hämtar eller sätter[`NumeralFormat`](../../numeralformat/) används för återgivning av siffror. Europeiska siffror används som standard.

```csharp
public NumeralFormat NumeralFormat { get; set; }
```

### Anmärkningar

Om värdet på den här egenskapen ändras och sidlayouten redan är byggd då [`UpdatePageLayout`](../../../aspose.words/document/updatepagelayout/) anropas automatiskt för att uppdatera eventuella ändringar.

### Exempel

Visar hur du ställer in det sifferformat som används när du sparar till PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = new CultureInfo("ar-AR").LCID;
builder.Writeln("1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 50, 100");

// Skapa ett "PdfSaveOptions"-objekt som vi kan skicka till dokumentets "Spara"-metod
// för att ändra hur den metoden konverterar dokumentet till .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Ställ in egenskapen "NumeralFormat" till "NumeralFormat.ArabicIndic" till
// använd glyfer från intervallet U+0660 till U+0669 som siffror.
// Ställ in egenskapen "NumeralFormat" till "NumeralFormat.Context" till
// slå upp språket för att avgöra hur många glyfer som ska användas.
// Ställ in egenskapen "NumeralFormat" till "NumeralFormat.EasternArabicIndic" till
// använd glyfer från intervallet U+06F0 till U+06F9 som siffror.
// Ställ in egenskapen "NumeralFormat" till "NumeralFormat.European" för att använda europeiska siffror.
// Ställ in egenskapen "NumeralFormat" till "NumeralFormat.System" för att bestämma symboluppsättningen från regionala inställningar.
options.NumeralFormat = numeralFormat;

doc.Save(ArtifactsDir + "PdfSaveOptions.SetNumeralFormat.pdf", options);
```

### Se även

* enum [NumeralFormat](../../numeralformat/)
* class [FixedPageSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../fixedpagesaveoptions/)
* hopsättning [Aspose.Words](../../../)


