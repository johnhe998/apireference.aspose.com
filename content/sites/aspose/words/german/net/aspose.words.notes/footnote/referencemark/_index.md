---
title: Footnote.ReferenceMark
second_title: Aspose.Words für .NET-API-Referenz
description: Footnote eigendom. Ruft/legt benutzerdefiniertes Referenzzeichen ab das für diese Fußnote verwendet werden soll. Standardwert ist leerer String Empty  was bedeutet dass automatisch nummerierte Fußnoten verwendet werden.
type: docs
weight: 50
url: /de/net/aspose.words.notes/footnote/referencemark/
---
## Footnote.ReferenceMark property

Ruft/legt benutzerdefiniertes Referenzzeichen ab, das für diese Fußnote verwendet werden soll. Standardwert ist **leerer String** (Empty ), was bedeutet, dass automatisch nummerierte Fußnoten verwendet werden.

```csharp
public string ReferenceMark { get; set; }
```

### Bemerkungen

Wenn diese Eigenschaft auf eingestellt ist **leerer String** (Empty ) oder null, dann[`IsAuto`](../isauto/) Die Eigenschaft wird automatisch auf true gesetzt, , wenn sie auf etwas anderes gesetzt wird[`IsAuto`](../isauto/) wird auf false gesetzt.

Das RTF-Format kann nur 1 Symbol als benutzerdefinierte Referenzmarke speichern, daher wird beim Exportieren nur das erste Symbol geschrieben, andere werden verworfen.

### Beispiele

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

* class [Footnote](../)
* namensraum [Aspose.Words.Notes](../../footnote/)
* Montage [Aspose.Words](../../../)


