---
title: XpsSaveOptions.OutlineOptions
second_title: Aspose.Words für .NET-API-Referenz
description: XpsSaveOptions eigendom. Ermöglicht das Festlegen von Gliederungsoptionen.
type: docs
weight: 20
url: /de/net/aspose.words.saving/xpssaveoptions/outlineoptions/
---
## XpsSaveOptions.OutlineOptions property

Ermöglicht das Festlegen von Gliederungsoptionen.

```csharp
public OutlineOptions OutlineOptions { get; }
```

### Bemerkungen

Beachten Sie, dass die Option ExpandedOutlineLevels beim Speichern in XPS nicht funktioniert.

### Beispiele

Zeigt, wie die Ebene der Überschriften eingeschränkt wird, die in der Gliederung eines gespeicherten XPS-Dokuments angezeigt werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Überschriften einfügen, die als Inhaltsverzeichniseinträge der Ebenen 1, 2 und dann 3 dienen können.
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

Assert.True(builder.ParagraphFormat.IsHeading);

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 1.2.1");
builder.Writeln("Heading 1.2.2");

// Erstellen Sie ein "XpsSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
// um zu ändern, wie diese Methode das Dokument in .XPS konvertiert.
XpsSaveOptions saveOptions = new XpsSaveOptions();

Assert.AreEqual(SaveFormat.Xps, saveOptions.SaveFormat);

// Das ausgegebene XPS-Dokument enthält eine Gliederung, ein Inhaltsverzeichnis, das Überschriften im Hauptteil des Dokuments auflistet.
// Durch Klicken auf einen Eintrag in dieser Gliederung gelangen wir zur Position der entsprechenden Überschrift.
// Setzen Sie die Eigenschaft "HeadingsOutlineLevels" auf "2", um alle Überschriften, deren Ebenen höher als 2 sind, von der Gliederung auszuschließen.
// Die letzten beiden Überschriften, die wir oben eingefügt haben, werden nicht angezeigt.
saveOptions.OutlineOptions.HeadingsOutlineLevels = 2;

doc.Save(ArtifactsDir + "XpsSaveOptions.OutlineLevels.xps", saveOptions);
```

### Siehe auch

* class [OutlineOptions](../../outlineoptions/)
* class [XpsSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../xpssaveoptions/)
* Montage [Aspose.Words](../../../)


