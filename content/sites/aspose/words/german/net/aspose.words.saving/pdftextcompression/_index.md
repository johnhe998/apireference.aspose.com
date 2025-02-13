---
title: Enum PdfTextCompression
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Saving.PdfTextCompression opsomming. Gibt einen Komprimierungstyp an der auf alle Inhalte in der PDFDatei mit Ausnahme von Bildern angewendet wird.
type: docs
weight: 5250
url: /de/net/aspose.words.saving/pdftextcompression/
---
## PdfTextCompression enumeration

Gibt einen Komprimierungstyp an, der auf alle Inhalte in der PDF-Datei mit Ausnahme von Bildern angewendet wird.

```csharp
public enum PdfTextCompression
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| None | `0` | Keine Komprimierung. |
| Flate | `1` | Flate (ZIP)-Komprimierung. |

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

* namensraum [Aspose.Words.Saving](../../aspose.words.saving/)
* Montage [Aspose.Words](../../)


