---
title: FieldGoToButton.DisplayText
second_title: Aspose.Words für .NET-API-Referenz
description: FieldGoToButton eigendom. Liest oder setzt den Text der Schaltfläche die im Dokument erscheint so dass sie ausgewählt werden kann um den Sprung zu aktivieren.
type: docs
weight: 20
url: /de/net/aspose.words.fields/fieldgotobutton/displaytext/
---
## FieldGoToButton.DisplayText property

Liest oder setzt den Text der "Schaltfläche", die im Dokument erscheint, so dass sie ausgewählt werden kann, um den Sprung zu aktivieren.

```csharp
public string DisplayText { get; set; }
```

### Beispiele

Zeigt das Einfügen eines GOTOBUTTON-Felds an.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ein GOTOBUTTON-Feld hinzufügen. Wenn wir in Microsoft Word auf dieses Feld doppelklicken,
// Der Textcursor wird zu dem Lesezeichen geführt, dessen Name von der Location-Eigenschaft referenziert wird.
FieldGoToButton field = (FieldGoToButton)builder.InsertField(FieldType.FieldGoToButton, true);
field.DisplayText = "My Button";
field.Location = "MyBookmark";

Assert.AreEqual(" GOTOBUTTON  MyBookmark My Button", field.GetFieldCode());

// Ein gültiges Lesezeichen für das zu referenzierende Feld einfügen.
builder.InsertBreak(BreakType.PageBreak);
builder.StartBookmark(field.Location);
builder.Writeln("Bookmark text contents.");
builder.EndBookmark(field.Location);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.GOTOBUTTON.docx");
```

### Siehe auch

* class [FieldGoToButton](../)
* namensraum [Aspose.Words.Fields](../../fieldgotobutton/)
* Montage [Aspose.Words](../../../)


