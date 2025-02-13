---
title: ParagraphFormat.Bidi
second_title: Aspose.Words für .NET-API-Referenz
description: ParagraphFormat eigendom. Ruft ab oder legt fest ob es sich um einen rechtsnachlinksAbsatz handelt.
type: docs
weight: 40
url: /de/net/aspose.words/paragraphformat/bidi/
---
## ParagraphFormat.Bidi property

Ruft ab oder legt fest, ob es sich um einen rechts-nach-links-Absatz handelt.

```csharp
public bool Bidi { get; set; }
```

### Bemerkungen

Wenn wahr, werden die Läufe und andere Inline-Objekte in diesem Absatz von rechts nach links angeordnet.

### Beispiele

Zeigt, wie die Textrichtung von Klartextdokumenten erkannt wird.

```csharp
// Erstellen Sie ein "TxtLoadOptions"-Objekt, das wir an den Konstruktor eines Dokuments übergeben können
// um zu ändern, wie wir ein Klartextdokument laden.
TxtLoadOptions loadOptions = new TxtLoadOptions();

// Setzen Sie die Eigenschaft "DocumentDirection" auf "DocumentDirection.Auto" wird automatisch erkannt
// die Richtung jedes Textabsatzes, den Aspose.Words aus Klartext lädt.
// Die "Bidi"-Eigenschaft jedes Absatzes speichert seine Richtung.
loadOptions.DocumentDirection = DocumentDirection.Auto;

// Hebräischen Text von rechts nach links erkennen.
Document doc = new Document(MyDir + "Hebrew text.txt", loadOptions);

Assert.True(doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Bidi);

// Englischen Text von rechts nach links erkennen.
doc = new Document(MyDir + "English text.txt", loadOptions);

Assert.False(doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Bidi);
```

Zeigt, wie von rechts nach links kompatible Listen mit BIDIOUTLINE-Feldern erstellt werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Das Feld BIDIOUTLINE nummeriert Absätze wie die Felder AUTONUM/LISTNUM,
// ist aber nur sichtbar, wenn eine Rechts-nach-links-Bearbeitungssprache aktiviert ist, z. B. Hebräisch oder Arabisch.
// Das folgende Feld zeigt ".1" an, das RTL-Äquivalent der Listennummer "1.".
FieldBidiOutline field = (FieldBidiOutline)builder.InsertField(FieldType.FieldBidiOutline, true);
builder.Writeln("שלום");

Assert.AreEqual(" BIDIOUTLINE ", field.GetFieldCode());

// Fügen Sie zwei weitere BIDIOUTLINE-Felder hinzu, die ".2" und ".3" anzeigen.
builder.InsertField(FieldType.FieldBidiOutline, true);
builder.Writeln("שלום");
builder.InsertField(FieldType.FieldBidiOutline, true);
builder.Writeln("שלום");

// Legen Sie die horizontale Textausrichtung für jeden Absatz im Dokument auf RTL fest.
foreach (Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.Bidi = true;
}

// Wenn wir in Microsoft Word eine Bearbeitungssprache von rechts nach links aktivieren, zeigen unsere Felder Zahlen an.
// Andernfalls wird "###" angezeigt.
doc.Save(ArtifactsDir + "Field.BIDIOUTLINE.docx");
```

### Siehe auch

* class [ParagraphFormat](../)
* namensraum [Aspose.Words](../../paragraphformat/)
* Montage [Aspose.Words](../../../)


