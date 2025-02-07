---
title: PdfSaveOptions.ImageCompression
second_title: Aspose.Words für .NET-API-Referenz
description: PdfSaveOptions eigendom. Gibt den Komprimierungstyp an der für alle Bilder im Dokument verwendet werden soll.
type: docs
weight: 170
url: /de/net/aspose.words.saving/pdfsaveoptions/imagecompression/
---
## PdfSaveOptions.ImageCompression property

Gibt den Komprimierungstyp an, der für alle Bilder im Dokument verwendet werden soll.

```csharp
public PdfImageCompression ImageCompression { get; set; }
```

### Bemerkungen

Standard istAuto.

VerwendenJpeg können Sie die Qualität der Bilder im Ausgabedokument über steuern[`JpegQuality`](../jpegquality/) Eigentum.

VerwendenJpeg bietet die schnellste Konvertierungsgeschwindigkeit im Vergleich zur Leistung anderer Komprimierungstypen, , aber in diesem Fall gibt es eine verlustbehaftete JPEG-Komprimierung.

VerwendenAuto können Sie die Qualität von JPEG im Ausgabedokument über steuern[`JpegQuality`](../jpegquality/) -Eigenschaft, , aber für andere Formate werden Rohpixeldaten extrahiert und mit Flate-Komprimierung gespeichert. Dieser Fall ist langsamer als die JPEG-Konvertierung, aber verlustfrei.

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

* enum [PdfImageCompression](../../pdfimagecompression/)
* class [PdfSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../pdfsaveoptions/)
* Montage [Aspose.Words](../../../)


