---
title: PageSetup.SuppressEndnotes
second_title: Aspose.Words für .NET-API-Referenz
description: PageSetup eigendom. WAHR wenn Endnoten am Ende des nächsten Abschnitts gedruckt werden der Endnoten nicht unterdrückt. Unterdrückte Endnoten werden vor den Endnoten in diesem Abschnitt gedruckt.
type: docs
weight: 400
url: /de/net/aspose.words/pagesetup/suppressendnotes/
---
## PageSetup.SuppressEndnotes property

**WAHR** wenn Endnoten am Ende des nächsten Abschnitts gedruckt werden, der Endnoten nicht unterdrückt. Unterdrückte Endnoten werden vor den Endnoten in diesem Abschnitt gedruckt.

```csharp
public bool SuppressEndnotes { get; set; }
```

### Beispiele

Zeigt, wie Endnoten am Ende jedes Abschnitts gespeichert und ihre Positionen geändert werden.

```csharp
{
    Document doc = new Document();
    doc.RemoveAllChildren();

     // Standardmäßig stellt ein Dokument alle Endnoten an seinem Ende zusammen.
    Assert.AreEqual(EndnotePosition.EndOfDocument, doc.EndnoteOptions.Position);

    // Wir verwenden die Eigenschaft "Position" des Objekts "EndnoteOptions" des Dokuments
     // um stattdessen Endnoten am Ende jedes Abschnitts zu sammeln.
    doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

    InsertSectionWithEndnote(doc, "Section 1", "Endnote 1, will stay in section 1");
    InsertSectionWithEndnote(doc, "Section 2", "Endnote 2, will be pushed down to section 3");
    InsertSectionWithEndnote(doc, "Section 3", "Endnote 3, will stay in section 3");

    // Während Abschnitte dazu gebracht werden, ihre jeweiligen Endnoten anzuzeigen, können wir das Flag "SuppressEndnotes" setzen
    // des "PageSetup"-Objekts eines Abschnitts auf "true", um zum Standardverhalten zurückzukehren und seine Endnoten zu übergeben
    // zum nächsten Abschnitt.
    PageSetup pageSetup = doc.Sections[1].PageSetup;
    pageSetup.SuppressEndnotes = true;

    doc.Save(ArtifactsDir + "PageSetup.SuppressEndnotes.docx");

/// <summary>
/// Einen Abschnitt mit Text und einer Endnote an ein Dokument anhängen.
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

### Siehe auch

* class [PageSetup](../)
* namensraum [Aspose.Words](../../pagesetup/)
* Montage [Aspose.Words](../../../)


