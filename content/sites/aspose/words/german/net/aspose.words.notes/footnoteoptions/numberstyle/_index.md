---
title: FootnoteOptions.NumberStyle
second_title: Aspose.Words für .NET-API-Referenz
description: FootnoteOptions eigendom. Gibt das Zahlenformat für automatisch nummerierte Fußnoten an.
type: docs
weight: 20
url: /de/net/aspose.words.notes/footnoteoptions/numberstyle/
---
## FootnoteOptions.NumberStyle property

Gibt das Zahlenformat für automatisch nummerierte Fußnoten an.

```csharp
public NumberStyle NumberStyle { get; set; }
```

### Bemerkungen

Nicht alle Zahlenstile sind für diese Eigenschaft anwendbar. Eine Liste der anwendbaren -Zahlenstile finden Sie im Dialogfeld „Fußnote oder Endnote einfügen“ in Microsoft Word. Wenn Sie einen nicht zutreffenden Zahlenstil auswählen, kehrt Microsoft Word zu einem Standardwert zurück.

### Beispiele

Zeigt, wie Sie den Nummernstil von Fußnoten-/Endnotenreferenzzeichen ändern.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fußnoten und Endnoten sind eine Möglichkeit, eine Referenz oder einen Nebenkommentar an Text anzuhängen
// das den Fluss des Haupttextes nicht stört. 
// Das Einfügen einer Fußnote/Endnote fügt ein kleines hochgestelltes Referenzsymbol hinzu
// am Haupttext, wo wir die Fußnote/Endnote einfügen.
// Jede Fußnote/Endnote erzeugt auch einen Eintrag, der aus einem zur Referenz passenden Symbol besteht
// Symbol im Haupttext. Der Referenztext, den wir an die „InsertEndnote“-Methode des Dokumenterstellers übergeben.
// Fußnoteneinträge werden standardmäßig unten auf jeder Seite angezeigt, die enthält
// ihre Referenzsymbole und Endnoten erscheinen am Ende des Dokuments.
builder.Write("Text 1. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 1.");
builder.Write("Text 2. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 2.");
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 3.", "Custom footnote reference mark");

builder.InsertParagraph();

builder.Write("Text 1. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 1.");
builder.Write("Text 2. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 2.");
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 3.", "Custom endnote reference mark");

// Standardmäßig ist das Referenzsymbol für jede Fußnote und Endnote ihr Index
// unter allen Fußnoten/Endnoten des Dokuments. Jedes Dokument behält separate Zählungen bei
// für Fußnoten und für Endnoten. Standardmäßig zeigen Fußnoten ihre Nummern mit arabischen Ziffern an,
// und Endnoten zeigen ihre Nummern in kleinen römischen Ziffern an.
Assert.AreEqual(NumberStyle.Arabic, doc.FootnoteOptions.NumberStyle);
Assert.AreEqual(NumberStyle.LowercaseRoman, doc.EndnoteOptions.NumberStyle);

// Wir können die Eigenschaft "NumberStyle" verwenden, um benutzerdefinierte Nummerierungsstile auf Fußnoten und Endnoten anzuwenden.
// Dies wirkt sich nicht auf Fußnoten/Endnoten mit benutzerdefinierten Referenzzeichen aus.
doc.FootnoteOptions.NumberStyle = NumberStyle.UppercaseRoman;
doc.EndnoteOptions.NumberStyle = NumberStyle.UppercaseLetter;

doc.Save(ArtifactsDir + "InlineStory.RefMarkNumberStyle.docx");
```

### Siehe auch

* enum [NumberStyle](../../../aspose.words/numberstyle/)
* class [FootnoteOptions](../)
* namensraum [Aspose.Words.Notes](../../footnoteoptions/)
* Montage [Aspose.Words](../../../)


