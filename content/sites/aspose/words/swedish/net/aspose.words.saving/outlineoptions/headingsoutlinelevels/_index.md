---
title: OutlineOptions.HeadingsOutlineLevels
second_title: Aspose.Words för .NET API Referens
description: OutlineOptions fast egendom. Anger hur många nivåer av rubriker stycken formaterade med rubrikstilar som ska inkluderas i dokumentkonturen.
type: docs
weight: 70
url: /sv/net/aspose.words.saving/outlineoptions/headingsoutlinelevels/
---
## OutlineOptions.HeadingsOutlineLevels property

Anger hur många nivåer av rubriker (stycken formaterade med rubrikstilar) som ska inkluderas i dokumentkonturen.

```csharp
public int HeadingsOutlineLevels { get; set; }
```

### Anmärkningar

Ange 0 för inga rubriker i dispositionen; ange 1 för en nivå av rubriker i dispositionen och så vidare.

Standard är 0. Giltigt intervall är 0 till 9.

### Exempel

Visar hur man konverterar ett helt dokument till PDF med tre nivåer i dokumentöversikten.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Infoga rubriker för nivåerna 1 till 5.
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

Assert.True(builder.ParagraphFormat.IsHeading);

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 1.2.1");
builder.Writeln("Heading 1.2.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading4;

builder.Writeln("Heading 1.2.2.1");
builder.Writeln("Heading 1.2.2.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading5;

builder.Writeln("Heading 1.2.2.2.1");
builder.Writeln("Heading 1.2.2.2.2");

// Skapa ett "PdfSaveOptions"-objekt som vi kan skicka till dokumentets "Spara"-metod
// för att ändra hur den metoden konverterar dokumentet till .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Det utgående PDF-dokumentet kommer att innehålla en disposition, som är en innehållsförteckning som listar rubriker i dokumentets brödtext.
// Genom att klicka på en post i denna disposition kommer vi till platsen för dess respektive rubrik.
// Ställ in egenskapen "HeadingsOutlineLevels" till "4" för att utesluta alla rubriker vars nivåer är över 4 från dispositionen.
options.OutlineOptions.HeadingsOutlineLevels = 4;

// Om en konturpost har efterföljande poster på en högre nivå mellan sig och nästa post på samma eller lägre nivå,
// en pil visas till vänster om posten. Denna post är "ägare" till flera sådana "underposter".
// I vårt dokument är dispositionsposterna från den 5:e rubriknivån underposter till den andra 4:e nivåns dispositionspost,
  // posterna på 4:e och 5:e rubriknivån är underposter till den andra 3:e nivåposten, och så vidare.
// I dispositionen kan vi klicka på pilen för "ägare"-posten för att komprimera/expandera alla dess underposter.
// Ställ in egenskapen "ExpandedOutlineLevels" till "2" för att automatiskt utöka alla rubriknivå 2 och lägre dispositionsposter
 // och kollapsa alla nivåer och 3 och högre poster när vi öppnar dokumentet.
options.OutlineOptions.ExpandedOutlineLevels = 2;

doc.Save(ArtifactsDir + "PdfSaveOptions.ExpandedOutlineLevels.pdf", options);
```

### Se även

* class [OutlineOptions](../)
* namnutrymme [Aspose.Words.Saving](../../outlineoptions/)
* hopsättning [Aspose.Words](../../../)


