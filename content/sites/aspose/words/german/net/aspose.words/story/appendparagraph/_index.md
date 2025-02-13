---
title: Story.AppendParagraph
second_title: Aspose.Words für .NET-API-Referenz
description: Story methode. Eine ShortcutMethode die a erstelltParagraph Objekt mit optionalem Text und fügt ihn an das Ende dieses Objekts an.
type: docs
weight: 60
url: /de/net/aspose.words/story/appendparagraph/
---
## Story.AppendParagraph method

Eine Shortcut-Methode, die a erstellt[`Paragraph`](../../paragraph/) Objekt mit optionalem Text und fügt ihn an das Ende dieses Objekts an.

```csharp
public Paragraph AppendParagraph(string text)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| text | String | Der Text für den Absatz. Kann null oder eine leere Zeichenfolge sein. |

### Rückgabewert

Der neu erstellte und angehängte Absatz.

### Beispiele

Zeigt, wie Sie eine Kopf- und eine Fußzeile erstellen.

```csharp
Document doc = new Document();

// Erstellen Sie eine Kopfzeile und hängen Sie einen Absatz daran an. Der Text in diesem Absatz
// erscheint oben auf jeder Seite dieses Abschnitts über dem Haupttext.
HeaderFooter header = new HeaderFooter(doc, HeaderFooterType.HeaderPrimary);
doc.FirstSection.HeadersFooters.Add(header);

Paragraph para = header.AppendParagraph("My header.");

Assert.True(header.IsHeader);
Assert.True(para.IsEndOfHeaderFooter);

// Erstellen Sie eine Fußzeile und hängen Sie einen Absatz daran an. Der Text in diesem Absatz
// wird unten auf jeder Seite dieses Abschnitts unter dem Haupttext angezeigt.
HeaderFooter footer = new HeaderFooter(doc, HeaderFooterType.FooterPrimary);
doc.FirstSection.HeadersFooters.Add(footer);

para = footer.AppendParagraph("My footer.");

Assert.False(footer.IsHeader);
Assert.True(para.IsEndOfHeaderFooter);

Assert.AreEqual(footer, para.ParentStory);
Assert.AreEqual(footer.ParentSection, para.ParentSection);
Assert.AreEqual(footer.ParentSection, header.ParentSection);

doc.Save(ArtifactsDir + "HeaderFooter.Create.docx");
```

### Siehe auch

* class [Paragraph](../../paragraph/)
* class [Story](../)
* namensraum [Aspose.Words](../../story/)
* Montage [Aspose.Words](../../../)


