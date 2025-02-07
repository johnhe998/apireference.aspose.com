---
title: PdfSaveOptions.ImageColorSpaceExportMode
second_title: Aspose.Words für .NET-API-Referenz
description: PdfSaveOptions eigendom. Gibt an wie der Farbraum für die Bilder im PDFDokument ausgewählt wird.
type: docs
weight: 160
url: /de/net/aspose.words.saving/pdfsaveoptions/imagecolorspaceexportmode/
---
## PdfSaveOptions.ImageColorSpaceExportMode property

Gibt an, wie der Farbraum für die Bilder im PDF-Dokument ausgewählt wird.

```csharp
public PdfImageColorSpaceExportMode ImageColorSpaceExportMode { get; set; }
```

### Bemerkungen

Der Standardwert istAuto .

WennSimpleCmyk Wert ist angegeben, [`ImageCompression`](../imagecompression/) Option wird ignoriert und Flate-Komprimierung wird für alle Bilder im Dokument verwendet.

SimpleCmyk Wert wird beim Speichern in PDF/A nicht unterstützt. Auto Wert wird stattdessen verwendet.

### Beispiele

Zeigt, wie Sie einen anderen Farbraum für Bilder in einem Dokument festlegen, wenn wir es in PDF exportieren.

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

// Legen Sie die Eigenschaft "ImageColorSpaceExportMode" auf "PdfImageColorSpaceExportMode.Auto" fest, um Aspose.Words zu erhalten
// wählt automatisch den Farbraum für Bilder in dem Dokument aus, das es in PDF konvertiert.
// In den meisten Fällen ist der Farbraum RGB.
// Setzen Sie die Eigenschaft "ImageColorSpaceExportMode" auf "PdfImageColorSpaceExportMode.SimpleCmyk"
// um den CMYK-Farbraum für alle Bilder im gespeicherten PDF zu verwenden.
// Aspose.Words wendet auch die Flate-Komprimierung auf alle Bilder an und ignoriert den Wert der Eigenschaft "ImageCompression".
pdfSaveOptions.ImageColorSpaceExportMode = pdfImageColorSpaceExportMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.ImageColorSpaceExportMode.pdf", pdfSaveOptions);
```

### Siehe auch

* enum [PdfImageColorSpaceExportMode](../../pdfimagecolorspaceexportmode/)
* class [PdfSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../pdfsaveoptions/)
* Montage [Aspose.Words](../../../)


