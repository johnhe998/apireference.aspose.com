---
title: Enum PdfImageCompression
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Saving.PdfImageCompression opsomming. Gibt den Komprimierungstyp an der auf Bilder in der PDFDatei angewendet wird.
type: docs
weight: 5210
url: /de/net/aspose.words.saving/pdfimagecompression/
---
## PdfImageCompression enumeration

Gibt den Komprimierungstyp an, der auf Bilder in der PDF-Datei angewendet wird.

```csharp
public enum PdfImageCompression
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| Auto | `0` | Wählt automatisch die am besten geeignete Komprimierung für jedes Bild aus. |
| Jpeg | `1` | JPEG-Komprimierung. Unterstützt keine Transparenz. |

### Beispiele

Zeigt, wie Sie einen Komprimierungstyp für alle Bilder in einem Dokument angeben, das wir in PDF konvertieren.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Jpeg image:");
builder.InsertImage(ImageDir + "Logo.jpg");
builder.InsertParagraph();
builder.Writeln("Png image:");
builder.InsertImage(ImageDir + "Transparent background logo.png");

// Erstellen Sie ein "PdfSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
// um zu ändern, wie diese Methode das Dokument in .PDF konvertiert.
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();

// Legen Sie die Eigenschaft "ImageCompression" auf "PdfImageCompression.Auto" fest, um die zu verwenden
// "ImageCompression"-Eigenschaft, um die Qualität der Jpeg-Bilder zu steuern, die in der Ausgabe-PDF enden.
// Legen Sie die Eigenschaft "ImageCompression" auf "PdfImageCompression.Jpeg" fest, um die zu verwenden
// "ImageCompression"-Eigenschaft zur Steuerung der Qualität aller Bilder, die im Ausgabe-PDF landen.
pdfSaveOptions.ImageCompression = pdfImageCompression;

// Setzen Sie die Eigenschaft "JpegQuality" auf "10", um die Komprimierung auf Kosten der Bildqualität zu verstärken.
pdfSaveOptions.JpegQuality = 10;

doc.Save(ArtifactsDir + "PdfSaveOptions.ImageCompression.pdf", pdfSaveOptions);
```

### Siehe auch

* namensraum [Aspose.Words.Saving](../../aspose.words.saving/)
* Montage [Aspose.Words](../../)


