---
title: Document.Sections
second_title: Aspose.Words för .NET API Referens
description: Document fast egendom. Returnerar en samling som representerar alla avsnitt i dokumentet.
type: docs
weight: 350
url: /sv/net/aspose.words/document/sections/
---
## Document.Sections property

Returnerar en samling som representerar alla avsnitt i dokumentet.

```csharp
public SectionCollection Sections { get; }
```

### Exempel

Visar hur man lägger till och tar bort avsnitt i ett dokument.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Section 1");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Section 2");

Assert.AreEqual("Section 1\x000cSection 2", doc.GetText().Trim());

// Ta bort det första avsnittet från dokumentet.
doc.Sections.RemoveAt(0);

Assert.AreEqual("Section 2", doc.GetText().Trim());

// Lägg till en kopia av det som nu är det första avsnittet i slutet av dokumentet.
int lastSectionIdx = doc.Sections.Count - 1;
Section newSection = doc.Sections[lastSectionIdx].Clone();
doc.Sections.Add(newSection);

Assert.AreEqual("Section 2\x000cSection 2", doc.GetText().Trim());
```

Visar hur man anger hur ett nytt avsnitt skiljer sig från det tidigare.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This text is in section 1.");

// Avsnittsbrytningstyper avgör hur ett nytt avsnitt skiljer sig från föregående avsnitt.
// Nedan finns fem typer av avsnittsbrytningar.
// 1 - Startar nästa avsnitt på en ny sida:
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Writeln("This text is in section 2.");

Assert.AreEqual(SectionStart.NewPage, doc.Sections[1].PageSetup.SectionStart);

// 2 - Startar nästa avsnitt på den aktuella sidan:
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("This text is in section 3.");

Assert.AreEqual(SectionStart.Continuous, doc.Sections[2].PageSetup.SectionStart);

// 3 - Startar nästa avsnitt på en ny jämn sida:
builder.InsertBreak(BreakType.SectionBreakEvenPage);
builder.Writeln("This text is in section 4.");

Assert.AreEqual(SectionStart.EvenPage, doc.Sections[3].PageSetup.SectionStart);

// 4 - Startar nästa avsnitt på en ny udda sida:
builder.InsertBreak(BreakType.SectionBreakOddPage);
builder.Writeln("This text is in section 5.");

Assert.AreEqual(SectionStart.OddPage, doc.Sections[4].PageSetup.SectionStart);

// 5 - Startar nästa avsnitt i en ny kolumn:
TextColumnCollection columns = builder.PageSetup.TextColumns;
columns.SetCount(2);

builder.InsertBreak(BreakType.SectionBreakNewColumn);
builder.Writeln("This text is in section 6.");

Assert.AreEqual(SectionStart.NewColumn, doc.Sections[5].PageSetup.SectionStart);

doc.Save(ArtifactsDir + "PageSetup.SetSectionStart.docx");
```

### Se även

* class [SectionCollection](../../sectioncollection/)
* class [Document](../)
* namnutrymme [Aspose.Words](../../document/)
* hopsättning [Aspose.Words](../../../)


