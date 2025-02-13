---
title: FieldShape.Text
second_title: Aspose.Words für .NET-API-Referenz
description: FieldShape eigendom. Ruft den abzurufenden Text ab oder legt ihn fest.
type: docs
weight: 20
url: /de/net/aspose.words.fields/fieldshape/text/
---
## FieldShape.Text property

Ruft den abzurufenden Text ab oder legt ihn fest.

```csharp
public string Text { get; set; }
```

### Beispiele

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

Zeigt, wie einige ältere Microsoft Word-Felder wie SHAPE und EMBED beim Laden behandelt werden.

```csharp
// Öffnen Sie ein Dokument, das in Microsoft Word 2003 erstellt wurde.
Document doc = new Document(MyDir + "Legacy fields.doc");

// Wenn wir das Word-Dokument öffnen und Alt+F9 drücken, sehen wir ein SHAPE- und ein EMBED-Feld.
// Ein SHAPE-Feld ist der Anker/Leinwand für ein AutoShape-Objekt mit aktiviertem Umbruchstil "In Linie mit Text".
// Ein EMBED-Feld hat die gleiche Funktion, aber für ein eingebettetes Objekt
// wie eine Tabelle aus einem externen Excel-Dokument.
// Diese Felder werden jedoch nicht in der Fields-Sammlung des Dokuments angezeigt.
Assert.AreEqual(0, doc.Range.Fields.Count);

// Diese Felder werden nur von alten Versionen von Microsoft Word unterstützt.
// Der Dokumentladeprozess konvertiert diese Felder in Shape-Objekte,
// auf die wir in der Knotensammlung des Dokuments zugreifen können.
NodeCollection shapes = doc.GetChildNodes(NodeType.Shape, true);
Assert.AreEqual(3, shapes.Count);

// Der erste Shape-Knoten entspricht dem SHAPE-Feld im Eingabedokument,
// Dies ist die Inline-Leinwand für die AutoForm.
Shape shape = (Shape)shapes[0];
Assert.AreEqual(ShapeType.Image, shape.ShapeType);

// Der zweite Shape-Knoten ist die AutoForm selbst.
shape = (Shape)shapes[1];
Assert.AreEqual(ShapeType.Can, shape.ShapeType);

// Die dritte Form ist das Feld EMBED, das die externe Tabelle enthielt.
shape = (Shape)shapes[2];
Assert.AreEqual(ShapeType.OleObject, shape.ShapeType);
```

### Siehe auch

* class [FieldShape](../)
* namensraum [Aspose.Words.Fields](../../fieldshape/)
* Montage [Aspose.Words](../../../)


