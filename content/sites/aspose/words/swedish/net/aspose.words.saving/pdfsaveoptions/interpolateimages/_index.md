---
title: PdfSaveOptions.InterpolateImages
second_title: Aspose.Words för .NET API Referens
description: PdfSaveOptions fast egendom. En flagga som indikerar om bildinterpolation ska utföras av en överensstämmande läsare. Närfalsk anges skrivs inte flaggan till utdatadokumentet och standardbeteendet för läsaren används istället.
type: docs
weight: 180
url: /sv/net/aspose.words.saving/pdfsaveoptions/interpolateimages/
---
## PdfSaveOptions.InterpolateImages property

En flagga som indikerar om bildinterpolation ska utföras av en överensstämmande läsare. När`falsk` anges, skrivs inte flaggan till utdatadokumentet och standardbeteendet för läsaren används istället.

```csharp
public bool InterpolateImages { get; set; }
```

### Anmärkningar

När upplösningen för en källbild är betydligt lägre än den för utenheten, täcker varje källexempel många enhetspixlar. Som ett resultat kan bilder verka taggiga eller blockiga. Dessa visuella artefakter kan reduceras genom att använda en bildinterpolationsalgoritm under renderingen. Istället för att måla alla pixlar som täcks av ett källexempel med samma färg, försöker bildinterpolation producera en jämn övergång mellan intilliggande exempelvärden.

En överensstämmande läsare kan välja att inte implementera den här funktionen i PDF, eller kan använda någon specifik implementering av interpolation som den vill.

Standardvärdet är`falsk`.

Interpolationsflagga är förbjuden av PDF/A-kompatibilitet.`falsk` värde kommer att användas automatiskt när du sparar till PDF/A.

### Exempel

Visar hur man utför interpolation på bilder samtidigt som man sparar ett dokument till PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Image img = Image.FromFile(ImageDir + "Transparent background logo.png");
builder.InsertImage(img);

// Skapa ett "PdfSaveOptions"-objekt som vi kan skicka till dokumentets "Spara"-metod
// för att ändra hur den metoden konverterar dokumentet till .PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Ställ in egenskapen "InterpolateImages" till "true" för att få läsaren som öppnar detta dokument att interpolera bilder.
// Deras upplösning bör vara lägre än den för enheten som visar dokumentet.
// Ställ in egenskapen "InterpolateImages" till "false" för att göra det så att läsaren inte tillämpar någon interpolation.
saveOptions.InterpolateImages = interpolateImages;

// När vi öppnar det här dokumentet med en läsare som Adobe Acrobat måste vi zooma in på bilden
// för att se interpolationseffekten om vi sparade dokumentet med det aktiverat.
doc.Save(ArtifactsDir + "PdfSaveOptions.InterpolateImages.pdf", saveOptions);
```

Visar hur man förbättrar kvaliteten på en bild i de renderade dokumenten (.NetStandard 2.0).

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (Image image = Image.Decode(ImageDir + "Transparent background logo.png"))
    builder.InsertImage(image);

// Skapa ett "PdfSaveOptions"-objekt som vi kan skicka till dokumentets "Spara"-metod
// för att ändra hur den metoden konverterar dokumentet till .PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Ställ in egenskapen "InterpolateImages" till "true" för att få läsaren som öppnar detta dokument att interpolera bilder.
// Deras upplösning bör vara lägre än den för enheten som visar dokumentet.
// Ställ in egenskapen "InterpolateImages" till "false" för att göra det så att läsaren inte tillämpar någon interpolation.
saveOptions.InterpolateImages = interpolateImages;

// När vi öppnar det här dokumentet med en läsare som Adobe Acrobat måste vi zooma in på bilden
// för att se interpolationseffekten om vi sparade dokumentet med det aktiverat.
doc.Save(ArtifactsDir + "PdfSaveOptions.InterpolateImagesNetStandard2.pdf", saveOptions);
```

### Se även

* class [PdfSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../pdfsaveoptions/)
* hopsättning [Aspose.Words](../../../)


