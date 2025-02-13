---
title: PageSetup.RtlGutter
second_title: Aspose.Words för .NET API Referens
description: PageSetup fast egendom. Hämtar eller ställer in om Microsoft Word använder rännstenar för sektionen baserat på ett språk från höger till vänster eller ett språk från vänster till höger.
type: docs
weight: 370
url: /sv/net/aspose.words/pagesetup/rtlgutter/
---
## PageSetup.RtlGutter property

Hämtar eller ställer in om Microsoft Word använder rännstenar för sektionen baserat på ett språk från höger till vänster eller ett språk från vänster till höger.

```csharp
public bool RtlGutter { get; set; }
```

### Exempel

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

* class [PageSetup](../)
* namnutrymme [Aspose.Words](../../pagesetup/)
* hopsättning [Aspose.Words](../../../)


