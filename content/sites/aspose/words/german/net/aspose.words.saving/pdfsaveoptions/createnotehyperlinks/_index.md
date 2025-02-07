---
title: PdfSaveOptions.CreateNoteHyperlinks
second_title: Aspose.Words für .NET-API-Referenz
description: PdfSaveOptions eigendom. Gibt an ob Fußnoten/Endnotenreferenzen im Haupttextabschnitt in aktive Hyperlinks umgewandelt werden sollen. Wenn der Hyperlink angeklickt wird führt er zur entsprechenden Fußnote/Endnote. Standard istFALSCH .
type: docs
weight: 40
url: /de/net/aspose.words.saving/pdfsaveoptions/createnotehyperlinks/
---
## PdfSaveOptions.CreateNoteHyperlinks property

Gibt an, ob Fußnoten-/Endnotenreferenzen im Haupttextabschnitt in aktive Hyperlinks umgewandelt werden sollen. Wenn der Hyperlink angeklickt wird, führt er zur entsprechenden Fußnote/Endnote. Standard ist`FALSCH` .

```csharp
public bool CreateNoteHyperlinks { get; set; }
```

### Beispiele

Zeigt, wie Fußnoten und Endnoten als Hyperlinks funktionieren.

```csharp
Document doc = new Document(MyDir + "Footnotes and endnotes.docx");

// Erstellen Sie ein "PdfSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
// um zu ändern, wie diese Methode das Dokument in .PDF konvertiert.
PdfSaveOptions options = new PdfSaveOptions();

// Setzen Sie die Eigenschaft "CreateNoteHyperlinks" auf "true", um alle Fußnoten-/Endnotensymbole umzuwandeln
// im Text fungieren als Links, die uns beim Anklicken zu den jeweiligen Fußnoten/Endnoten führen.
// Legen Sie die Eigenschaft "CreateNoteHyperlinks" auf "false" fest, um keine Fußnoten-/Endnotensymbole mit irgendetwas zu verknüpfen.
options.CreateNoteHyperlinks = createNoteHyperlinks;

doc.Save(ArtifactsDir + "PdfSaveOptions.NoteHyperlinks.pdf", options);
```

### Siehe auch

* class [PdfSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../pdfsaveoptions/)
* Montage [Aspose.Words](../../../)


