---
title: Body.ParentSection
second_title: Aspose.Words för .NET API Referens
description: Body fast egendom. Hämtar den överordnade delen av denna berättelse.
type: docs
weight: 30
url: /sv/net/aspose.words/body/parentsection/
---
## Body.ParentSection property

Hämtar den överordnade delen av denna berättelse.

```csharp
public Section ParentSection { get; }
```

### Anmärkningar

**Föräldrasektionen** är ekvivalent med`(Sektion) ParentNode`.

### Exempel

Visar hur man lagrar slutnoter i slutet av varje avsnitt och ändrar deras positioner.

```csharp
{
    Document doc = new Document();
    doc.RemoveAllChildren();

      // Som standard kompilerar ett dokument alla slutnoter i slutet.
    Assert.AreEqual(EndnotePosition.EndOfDocument, doc.EndnoteOptions.Position);

    // Vi använder egenskapen "Position" för dokumentets "EndnoteOptions"-objekt
     // för att samla slutnoter i slutet av varje avsnitt istället.
    doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

    InsertSectionWithEndnote(doc, "Section 1", "Endnote 1, will stay in section 1");
    InsertSectionWithEndnote(doc, "Section 2", "Endnote 2, will be pushed down to section 3");
    InsertSectionWithEndnote(doc, "Section 3", "Endnote 3, will stay in section 3");

    // När vi får avsnitt att visa sina respektive slutnoter kan vi ställa in flaggan "SuppressEndnotes"
    // av en sektions "PageSetup"-objekt till "true" för att återgå till standardbeteendet och skicka dess slutanteckningar
    // till nästa avsnitt.
    PageSetup pageSetup = doc.Sections[1].PageSetup;
    pageSetup.SuppressEndnotes = true;

    doc.Save(ArtifactsDir + "PageSetup.SuppressEndnotes.docx");

/// <summary>
/// Lägg till ett avsnitt med text och en slutnot till ett dokument.
/// </summary>
private static void InsertSectionWithEndnote(Document doc, string sectionBodyText, string endnoteText)
{
    Section section = new Section(doc);

    doc.AppendChild(section);

    Body body = new Body(doc);
    section.AppendChild(body);

    Assert.AreEqual(section, body.ParentNode);

    Paragraph para = new Paragraph(doc);
    body.AppendChild(para);

    Assert.AreEqual(body, para.ParentNode);

    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.MoveTo(para);
    builder.Write(sectionBodyText);
    builder.InsertFootnote(FootnoteType.Endnote, endnoteText);
}
```

### Se även

* class [Section](../../section/)
* class [Body](../)
* namnutrymme [Aspose.Words](../../body/)
* hopsättning [Aspose.Words](../../../)


