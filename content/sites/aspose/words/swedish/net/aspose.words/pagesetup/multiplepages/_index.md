---
title: PageSetup.MultiplePages
second_title: Aspose.Words för .NET API Referens
description: PageSetup fast egendom. För flersidiga dokument hämtar eller ställer in hur ett dokument skrivs ut eller återges så att det kan bindas in som ett häfte.
type: docs
weight: 260
url: /sv/net/aspose.words/pagesetup/multiplepages/
---
## PageSetup.MultiplePages property

För flersidiga dokument, hämtar eller ställer in hur ett dokument skrivs ut eller återges så att det kan bindas in som ett häfte.

```csharp
public MultiplePagesType MultiplePages { get; set; }
```

### Exempel

Visar hur man konfigurerar ett dokument som kan skrivas ut som en bokvikning.

```csharp
Document doc = new Document();

// Infoga text som sträcker sig över 16 sidor.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("My Booklet:");

for (int i = 0; i < 15; i++)
{
    builder.InsertBreak(BreakType.PageBreak);
    builder.Write($"Booklet face #{i}");
}

// Konfigurera den första sektionens "PageSetup"-egenskap för att skriva ut dokumentet i form av en bokvikning.
// När vi skriver ut det här dokumentet på båda sidor kan vi ta sidorna för att stapla dem
// och vik ner alla på mitten på en gång. Innehållet i dokumentet kommer att hamna i en bokveck.
PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.MultiplePages = MultiplePagesType.BookFoldPrinting;

// Vi kan bara ange antalet ark i multiplar av 4.
pageSetup.SheetsPerBooklet = 4;

doc.Save(ArtifactsDir + "PageSetup.Booklet.docx");
```

Visar hur man ställer in rännmarginaler.

```csharp
Document doc = new Document();

// Infoga text som sträcker sig över flera sidor.
DocumentBuilder builder = new DocumentBuilder(doc);
for (int i = 0; i < 6; i++)
{
    builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                  "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");
    builder.InsertBreak(BreakType.PageBreak);
}

// En ränna lägger till blanksteg till antingen vänster eller höger sidmarginal,
// som kompenserar för mittvikningen av sidor i en bok som inkräktar på sidans layout.
PageSetup pageSetup = doc.Sections[0].PageSetup;

  // Bestäm hur mycket utrymme våra sidor har för text inom marginalerna och lägg sedan till ett belopp för att fylla en marginal.
Assert.AreEqual(470.30d, pageSetup.PageWidth - pageSetup.LeftMargin - pageSetup.RightMargin, 0.01d);

pageSetup.Gutter = 100.0d;

// Ställ in egenskapen "RtlGutter" till "true" för att placera rännstenen i en mer lämplig position för text från höger till vänster.
pageSetup.RtlGutter = true;

// Ställ in "MultiplePages"-egenskapen till "MultiplePagesType.MirrorMargins" för att alternera
// vänster/höger sidas sidoposition för marginaler varje sida.
pageSetup.MultiplePages = MultiplePagesType.MirrorMargins;

doc.Save(ArtifactsDir + "PageSetup.Gutter.docx");
```

### Se även

* enum [MultiplePagesType](../../../aspose.words.settings/multiplepagestype/)
* class [PageSetup](../)
* namnutrymme [Aspose.Words](../../pagesetup/)
* hopsättning [Aspose.Words](../../../)


