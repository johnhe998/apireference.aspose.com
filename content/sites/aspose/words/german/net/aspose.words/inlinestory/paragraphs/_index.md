---
title: InlineStory.Paragraphs
second_title: Aspose.Words für .NET-API-Referenz
description: InlineStory eigendom. Ruft eine Sammlung von Absätzen ab die der Geschichte direkt untergeordnet sind.
type: docs
weight: 80
url: /de/net/aspose.words/inlinestory/paragraphs/
---
## InlineStory.Paragraphs property

Ruft eine Sammlung von Absätzen ab, die der Geschichte direkt untergeordnet sind.

```csharp
public ParagraphCollection Paragraphs { get; }
```

### Beispiele

Zeigt, wie Sie einem Absatz einen Kommentar hinzufügen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Hello world!");

Comment comment = new Comment(doc, "John Doe", "JD", DateTime.Today);
builder.CurrentParagraph.AppendChild(comment);
builder.MoveTo(comment.AppendChild(new Paragraph(doc)));
builder.Write("Comment text.");

Assert.AreEqual(DateTime.Today, comment.DateTime);

// In Microsoft Word können wir mit der rechten Maustaste auf diesen Kommentar im Dokumenttext klicken, um ihn zu bearbeiten oder darauf zu antworten. 
doc.Save(ArtifactsDir + "InlineStory.AddComment.docx");
```

Zeigt, wie Fußnoten eingefügt und angepasst werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Text hinzufügen und mit einer Fußnote darauf verweisen. Diese Fußnote platziert einen kleinen hochgestellten Verweis
// Markieren Sie nach dem Text, auf den es verweist, und erstellen Sie einen Eintrag unter dem Haupttext unten auf der Seite.
// Dieser Eintrag enthält das Referenzzeichen der Fußnote und den Referenztext,
// die wir an die "InsertFootnote"-Methode des Dokumenterstellers übergeben.
builder.Write("Main body text.");
Footnote footnote = builder.InsertFootnote(FootnoteType.Footnote, "Footnote text.");

// Wenn diese Eigenschaft auf "true" gesetzt ist, dann das Referenzzeichen unserer Fußnote
// wird sein Index unter allen Fußnoten des Abschnitts sein.
// Dies ist die erste Fußnote, also ist die Referenzmarke "1".
Assert.True(footnote.IsAuto);

// Wir können den Document Builder in die Fußnote verschieben, um seinen Referenztext zu bearbeiten. 
builder.MoveTo(footnote.FirstParagraph);
builder.Write(" More text added by a DocumentBuilder.");
builder.MoveToDocumentEnd();

Assert.AreEqual("\u0002 Footnote text. More text added by a DocumentBuilder.", footnote.GetText().Trim());

builder.Write(" More main body text.");
footnote = builder.InsertFootnote(FootnoteType.Footnote, "Footnote text.");

// Wir können eine benutzerdefinierte Referenzmarke setzen, die die Fußnote anstelle ihrer Indexnummer verwendet.
footnote.ReferenceMark = "RefMark";

Assert.False(footnote.IsAuto);

// Ein Lesezeichen, bei dem das Flag "IsAuto" auf "true" gesetzt ist, zeigt immer noch seinen echten Index
// Auch wenn frühere Lesezeichen benutzerdefinierte Referenzzeichen anzeigen, ist das Referenzzeichen dieses Lesezeichens eine "3".
builder.Write(" More main body text.");
footnote = builder.InsertFootnote(FootnoteType.Footnote, "Footnote text.");

Assert.True(footnote.IsAuto);

doc.Save(ArtifactsDir + "InlineStory.AddFootnote.docx");
```

### Siehe auch

* class [ParagraphCollection](../../paragraphcollection/)
* class [InlineStory](../)
* namensraum [Aspose.Words](../../inlinestory/)
* Montage [Aspose.Words](../../../)


