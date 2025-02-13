---
title: OleFormat.OleIcon
second_title: Aspose.Words für .NET-API-Referenz
description: OleFormat eigendom. Ruft den Zeichenaspekt des OLEObjekts ab. Wann Stimmt  wird das OLEObjekt als Symbol angezeigt. Wann FALSCH  wird das OLEObjekt als Inhalt angezeigt.
type: docs
weight: 70
url: /de/net/aspose.words.drawing/oleformat/oleicon/
---
## OleFormat.OleIcon property

Ruft den Zeichenaspekt des OLE-Objekts ab. Wann **Stimmt** , wird das OLE-Objekt als Symbol angezeigt. Wann **FALSCH** , wird das OLE-Objekt als Inhalt angezeigt.

```csharp
public bool OleIcon { get; }
```

### Bemerkungen

Aspose.Words erlaubt es nicht, diese Eigenschaft zu setzen, um Verwirrung zu vermeiden. Wenn Sie den Zeichenaspekt in Aspose.Words ändern könnten, würde Microsoft Word das OLE-Objekt immer noch in seinem ursprünglichen -Darstellungsaspekt anzeigen, bis Sie das OLE-Objekt in Microsoft Word bearbeiten oder aktualisieren.

### Beispiele

Zeigt, wie verknüpfte und nicht verknüpfte OLE-Objekte eingefügt werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Eine Microsoft Visio-Zeichnung als OLE-Objekt in das Dokument einbetten.
builder.InsertOleObject(ImageDir + "Microsoft Visio drawing.vsd", "Package", false, false, null);

// Einen Link auf die Datei im lokalen Dateisystem einfügen und als Icon anzeigen.
builder.InsertOleObject(ImageDir + "Microsoft Visio drawing.vsd", "Package", true, true, null);

// Durch das Einfügen von OLE-Objekten werden Formen erstellt, die diese Objekte speichern.
Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(2, shapes.Length);
Assert.AreEqual(2, shapes.Count(s => s.ShapeType == ShapeType.OleObject));

// Wenn eine Form ein OLE-Objekt enthält, hat sie eine gültige "OleFormat"-Eigenschaft,
// die wir verwenden können, um einige Aspekte der Form zu überprüfen.
OleFormat oleFormat = shapes[0].OleFormat;

Assert.AreEqual(false, oleFormat.IsLink);
Assert.AreEqual(false, oleFormat.OleIcon);

oleFormat = shapes[1].OleFormat;

Assert.AreEqual(true, oleFormat.IsLink);
Assert.AreEqual(true, oleFormat.OleIcon);

Assert.True(oleFormat.SourceFullName.EndsWith(@"Images" + Path.DirectorySeparatorChar + "Microsoft Visio drawing.vsd"));
Assert.AreEqual("", oleFormat.SourceItem);

Assert.AreEqual("Microsoft Visio drawing.vsd", oleFormat.IconCaption);

doc.Save(ArtifactsDir + "Shape.OleLinks.docx");

// Wenn das Objekt OLE-Daten enthält, können wir über einen Stream darauf zugreifen.
using (MemoryStream stream = oleFormat.GetOleEntry("\x0001CompObj"))
{
    byte[] oleEntryBytes = stream.ToArray();
    Assert.AreEqual(76, oleEntryBytes.Length);
}
```

### Siehe auch

* class [OleFormat](../)
* namensraum [Aspose.Words.Drawing](../../oleformat/)
* Montage [Aspose.Words](../../../)


