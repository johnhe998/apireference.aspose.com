---
title: PsSaveOptions.SaveFormat
second_title: Aspose.Words för .NET API Referens
description: PsSaveOptions fast egendom. Anger formatet som dokumentet kommer att sparas i om detta sparaalternativobjekt används. Kan endastPs .
type: docs
weight: 20
url: /sv/net/aspose.words.saving/pssaveoptions/saveformat/
---
## PsSaveOptions.SaveFormat property

Anger formatet som dokumentet kommer att sparas i om detta sparaalternativ-objekt används. Kan endastPs .

```csharp
public override SaveFormat SaveFormat { get; set; }
```

### Exempel

Visar hur man sparar ett dokument i Postscript-format i form av en bokvikning.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");

// Skapa ett "PsSaveOptions"-objekt som vi kan skicka till dokumentets "Spara"-metod
// för att ändra hur den metoden konverterar dokumentet till PostScript.
// Ställ in egenskapen "UseBookFoldPrintingSettings" till "true" för att ordna innehållet
// i det utgående Postscript-dokumentet på ett sätt som hjälper oss att göra ett häfte av det.
// Ställ in egenskapen "UseBookFoldPrintingSettings" till "false" för att spara dokumentet normalt.
PsSaveOptions saveOptions = new PsSaveOptions
{
    SaveFormat = SaveFormat.Ps,
    UseBookFoldPrintingSettings = renderTextAsBookFold
};

// Om vi renderar dokumentet som ett häfte måste vi ställa in "Flera sidor"
// egenskaper för sidinställningarna för alla sektioner till "MultiplePagesType.BookFoldPrinting".
foreach (Section s in doc.Sections)
{
    s.PageSetup.MultiplePages = MultiplePagesType.BookFoldPrinting;
}

// När vi har skrivit ut det här dokumentet på båda sidorna av sidorna kan vi vika alla sidor på mitten samtidigt,
// och innehållet kommer att radas upp på ett sätt som skapar ett häfte.
doc.Save(ArtifactsDir + "PsSaveOptions.UseBookFoldPrintingSettings.ps", saveOptions);
```

### Se även

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [PsSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../pssaveoptions/)
* hopsättning [Aspose.Words](../../../)


