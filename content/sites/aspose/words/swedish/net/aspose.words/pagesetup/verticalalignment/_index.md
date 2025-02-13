---
title: PageSetup.VerticalAlignment
second_title: Aspose.Words för .NET API Referens
description: PageSetup fast egendom. Returnerar eller ställer in den vertikala justeringen av text på varje sida i ett dokument eller avsnitt.
type: docs
weight: 440
url: /sv/net/aspose.words/pagesetup/verticalalignment/
---
## PageSetup.VerticalAlignment property

Returnerar eller ställer in den vertikala justeringen av text på varje sida i ett dokument eller avsnitt.

```csharp
public PageVerticalAlignment VerticalAlignment { get; set; }
```

### Exempel

Visar hur man tillämpar och återställer sidinställningar till avsnitt i ett dokument.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ändra sidinställningarna för byggarens nuvarande avsnitt och lägg till text.
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.VerticalAlignment = PageVerticalAlignment.Center;
builder.Writeln("This is the first section, which landscape oriented with vertically centered text.");

// Om vi startar ett nytt avsnitt med hjälp av en dokumentbyggare,
// det kommer att ärva byggarens nuvarande sidinställningar.
builder.InsertBreak(BreakType.SectionBreakNewPage);

Assert.AreEqual(Orientation.Landscape, doc.Sections[1].PageSetup.Orientation);
Assert.AreEqual(PageVerticalAlignment.Center, doc.Sections[1].PageSetup.VerticalAlignment);

// Vi kan återställa dess sidinställningar till deras standardvärden med "ClearFormatting"-metoden.
builder.PageSetup.ClearFormatting();

Assert.AreEqual(Orientation.Portrait, doc.Sections[1].PageSetup.Orientation);
Assert.AreEqual(PageVerticalAlignment.Top, doc.Sections[1].PageSetup.VerticalAlignment);

builder.Writeln("This is the second section, which is in default Letter paper size, portrait orientation and top alignment.");

doc.Save(ArtifactsDir + "PageSetup.ClearFormatting.docx");
```

### Se även

* enum [PageVerticalAlignment](../../pageverticalalignment/)
* class [PageSetup](../)
* namnutrymme [Aspose.Words](../../pagesetup/)
* hopsättning [Aspose.Words](../../../)


