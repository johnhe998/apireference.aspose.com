---
title: FootnoteOptions.Position
second_title: Aspose.Words für .NET-API-Referenz
description: FootnoteOptions eigendom. Gibt die Position der Fußnoten an.
type: docs
weight: 30
url: /de/net/aspose.words.notes/footnoteoptions/position/
---
## FootnoteOptions.Position property

Gibt die Position der Fußnoten an.

```csharp
public FootnotePosition Position { get; set; }
```

### Beispiele

Zeigt, wie Sie einen anderen Ort auswählen, an dem das Dokument seine Fußnoten sammelt und anzeigt.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Eine Fußnote ist eine Möglichkeit, eine Referenz oder einen Seitenkommentar an einen Text anzuhängen
// das den Fluss des Haupttextes nicht stört.  
// Das Einfügen einer Fußnote fügt ein kleines hochgestelltes Referenzsymbol hinzu
// im Haupttext, wo wir die Fußnote einfügen.
// Jede Fußnote erzeugt auch einen Eintrag am Ende der Seite, bestehend aus einem Symbol
// das mit dem Referenzsymbol im Haupttext übereinstimmt.
// Der Referenztext, den wir an die "InsertFootnote"-Methode des Dokumenterstellers übergeben.
builder.Write("Hello world!");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote contents.");

// Wir können die Eigenschaft "Position" verwenden, um zu bestimmen, wo das Dokument alle seine Fußnoten platzieren wird.
// Wenn wir den Wert der Eigenschaft "Position" auf "FootnotePosition.BottomOfPage" setzen,
// Jede Fußnote wird unten auf der Seite angezeigt, die ihr Referenzzeichen enthält. Dies ist der Standardwert.
// Wenn wir den Wert der Eigenschaft "Position" auf "FootnotePosition.BeneathText" setzen,
// jede Fußnote erscheint am Ende des Seitentextes, der ihr Referenzzeichen enthält.
doc.FootnoteOptions.Position = footnotePosition;

doc.Save(ArtifactsDir + "InlineStory.PositionFootnote.docx");
```

### Siehe auch

* enum [FootnotePosition](../../footnoteposition/)
* class [FootnoteOptions](../)
* namensraum [Aspose.Words.Notes](../../footnoteoptions/)
* Montage [Aspose.Words](../../../)


