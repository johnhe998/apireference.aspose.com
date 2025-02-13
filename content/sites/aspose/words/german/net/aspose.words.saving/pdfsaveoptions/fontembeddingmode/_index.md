---
title: PdfSaveOptions.FontEmbeddingMode
second_title: Aspose.Words für .NET-API-Referenz
description: PdfSaveOptions eigendom. Gibt den Schriftarteinbettungsmodus an.
type: docs
weight: 140
url: /de/net/aspose.words.saving/pdfsaveoptions/fontembeddingmode/
---
## PdfSaveOptions.FontEmbeddingMode property

Gibt den Schriftarteinbettungsmodus an.

```csharp
public PdfFontEmbeddingMode FontEmbeddingMode { get; set; }
```

### Bemerkungen

Der Standardwert istEmbedAll.

Diese Einstellung funktioniert nur für Text in ANSI-Codierung (Windows-1252). Wenn das Dokument Nicht-ANSI-Text enthält, werden die entsprechenden Schriftarten unabhängig von dieser Einstellung eingebettet.

Die Einhaltung von PDF/A und PDF/UA erfordert die Einbettung aller Schriftarten. EmbedAll Wert wird automatisch beim Speichern in PDF/A und PDF/UA verwendet.

### Beispiele

Zeigt, wie Aspose.Words so eingestellt wird, dass das Einbetten von Arial- und Times New Roman-Schriftarten in ein PDF-Dokument übersprungen wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// "Arial" ist eine Standardschriftart und "Courier New" ist eine Nicht-Standardschriftart.
builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Courier New";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

// Erstellen Sie ein "PdfSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
// um zu ändern, wie diese Methode das Dokument in .PDF konvertiert.
PdfSaveOptions options = new PdfSaveOptions();

// Setzen Sie die Eigenschaft "EmbedFullFonts" auf "true", um jede Glyphe jeder eingebetteten Schriftart in die Ausgabe-PDF einzubetten.
options.EmbedFullFonts = true;

// Legen Sie die Eigenschaft „FontEmbeddingMode“ auf „EmbedAll“ fest, um alle Schriftarten in die Ausgabe-PDF einzubetten.
// Legen Sie die Eigenschaft „FontEmbeddingMode“ auf „EmbedNonstandard“ fest, um nur das Einbetten von nicht standardmäßigen Schriftarten in die Ausgabe-PDF zuzulassen.
// Legen Sie die Eigenschaft „FontEmbeddingMode“ auf „EmbedNone“ fest, um keine Schriftarten in die Ausgabe-PDF einzubetten.
options.FontEmbeddingMode = pdfFontEmbeddingMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.EmbedWindowsFonts.pdf", options);

switch (pdfFontEmbeddingMode)
{
    case PdfFontEmbeddingMode.EmbedAll:
        Assert.That(1000000, Is.LessThan(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedWindowsFonts.pdf").Length));
        break;
    case PdfFontEmbeddingMode.EmbedNonstandard:
        Assert.That(480000, Is.LessThan(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedWindowsFonts.pdf").Length));
        break;
    case PdfFontEmbeddingMode.EmbedNone:
        Assert.That(4217, Is.AtLeast(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedWindowsFonts.pdf").Length));
        break;
}
```

### Siehe auch

* enum [PdfFontEmbeddingMode](../../pdffontembeddingmode/)
* class [PdfSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../pdfsaveoptions/)
* Montage [Aspose.Words](../../../)


