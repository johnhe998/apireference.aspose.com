---
title: PdfSaveOptions.TextCompression
second_title: Aspose.Words für .NET-API-Referenz
description: PdfSaveOptions eigendom. Gibt den Komprimierungstyp an der für alle Textinhalte im Dokument verwendet werden soll.
type: docs
weight: 260
url: /de/net/aspose.words.saving/pdfsaveoptions/textcompression/
---
## PdfSaveOptions.TextCompression property

Gibt den Komprimierungstyp an, der für alle Textinhalte im Dokument verwendet werden soll.

```csharp
public PdfTextCompression TextCompression { get; set; }
```

### Bemerkungen

Standard istFlate.

Erhöht die Ausgabegröße erheblich, wenn ein Dokument ohne Komprimierung gespeichert wird.

### Beispiele

Zeigt, wie Textkomprimierung angewendet wird, wenn ein Dokument als PDF gespeichert wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

for (int i = 0; i < 100; i++)
    builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                    "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

// Erstellen Sie ein "PdfSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
// um zu ändern, wie diese Methode das Dokument in .PDF konvertiert.
PdfSaveOptions options = new PdfSaveOptions();

// Legen Sie die Eigenschaft "TextCompression" auf "PdfTextCompression.None" fest, um keine anzuwenden
// Komprimierung zu Text, wenn wir das Dokument als PDF speichern.
// Legen Sie die Eigenschaft „TextCompression“ auf „PdfTextCompression.Flate“ fest, um die ZIP-Komprimierung anzuwenden
// in Text, wenn wir das Dokument als PDF speichern. Je größer das Dokument, desto größer die Wirkung, die dies haben wird.
options.TextCompression = pdfTextCompression;

doc.Save(ArtifactsDir + "PdfSaveOptions.TextCompression.pdf", options);
```

### Siehe auch

* enum [PdfTextCompression](../../pdftextcompression/)
* class [PdfSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../pdfsaveoptions/)
* Montage [Aspose.Words](../../../)


