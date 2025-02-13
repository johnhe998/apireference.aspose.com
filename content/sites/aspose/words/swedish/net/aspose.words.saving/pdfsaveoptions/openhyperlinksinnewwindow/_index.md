---
title: PdfSaveOptions.OpenHyperlinksInNewWindow
second_title: Aspose.Words för .NET API Referens
description: PdfSaveOptions fast egendom. Hämtar eller ställer in ett värde som avgör om hyperlänkar i utdata Pdf document tvingas öppnas i ett nytt fönster eller flik i en webbläsare.
type: docs
weight: 200
url: /sv/net/aspose.words.saving/pdfsaveoptions/openhyperlinksinnewwindow/
---
## PdfSaveOptions.OpenHyperlinksInNewWindow property

Hämtar eller ställer in ett värde som avgör om hyperlänkar i utdata Pdf document tvingas öppnas i ett nytt fönster (eller flik) i en webbläsare.

```csharp
public bool OpenHyperlinksInNewWindow { get; set; }
```

### Anmärkningar

Standardvärdet är`falsk` . När detta värde är satt till`Sann` hyperlänkar sparas med JavaScript-kod. JavaScript-kod är`app.launchURL("URL", true);`, där`URL` är en hyperlänk.

Observera att om det här alternativet är inställt på`Sann` hyperlänkar kan inte fungera i vissa PDF-läsare, t.ex. Chrome, Firefox.

JavaScript-åtgärder är förbjudna av PDF/A-1 och PDF/A-2-kompatibilitet.`falsk` kommer att användas automatiskt när sparas till PDF/A-1 och PDF/A-2.

### Exempel

Visar hur man sparar hyperlänkar i ett dokument som vi konverterar till PDF så att de öppnar nya sidor när vi klickar på dem.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertHyperlink("Testlink", @"https://www.google.com/search?q=%20aspose", false);

// Skapa ett "PdfSaveOptions"-objekt som vi kan skicka till dokumentets "Spara"-metod
// för att ändra hur den metoden konverterar dokumentet till .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Ställ in egenskapen "OpenHyperlinksInNewWindow" till "true" för att spara alla hyperlänkar med Javascript-kod
// som tvingar läsarna att öppna dessa länkar i nya fönster/webbläsarflikar.
// Ställ in egenskapen "OpenHyperlinksInNewWindow" till "false" för att spara alla hyperlänkar normalt.
options.OpenHyperlinksInNewWindow = openHyperlinksInNewWindow;

doc.Save(ArtifactsDir + "PdfSaveOptions.OpenHyperlinksInNewWindow.pdf", options);
```

### Se även

* class [PdfSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../pdfsaveoptions/)
* hopsättning [Aspose.Words](../../../)


