---
title: PdfSaveOptions.UseCoreFonts
second_title: Aspose.Words für .NET-API-Referenz
description: PdfSaveOptions eigendom. Ruft einen Wert ab oder legt einen Wert fest der bestimmt ob die TrueTypeSchriftarten Arial Times New Roman Courier New und Symbol durch Core PDF Type 1Schriftarten ersetzt werden sollen oder nicht.
type: docs
weight: 280
url: /de/net/aspose.words.saving/pdfsaveoptions/usecorefonts/
---
## PdfSaveOptions.UseCoreFonts property

Ruft einen Wert ab oder legt einen Wert fest, der bestimmt, ob die TrueType-Schriftarten Arial, Times New Roman, Courier New und Symbol durch Core PDF Type 1-Schriftarten ersetzt werden sollen oder nicht.

```csharp
public bool UseCoreFonts { get; set; }
```

### Bemerkungen

Der Standardwert ist`FALSCH` . Wenn dieser Wert auf eingestellt ist`Stimmt` Die Schriftarten Arial, Times New Roman, Courier New und Symbol werden im PDF-Dokument durch die entsprechende Core Type 1-Schriftart ersetzt.

Grundlegende PDF-Schriftarten oder ihre Schriftartmetriken und geeignete Ersatzschriftarten müssen für alle PDF-Viewer-Anwendungen verfügbar sein.

Diese Einstellung funktioniert nur für Text in ANSI-Codierung (Windows-1252). Nicht-ANSI-Text wird unabhängig von dieser Einstellung mit eingebetteter TrueType-Schrift geschrieben .

Die Einhaltung von PDF/A und PDF/UA erfordert die Einbettung aller Schriftarten.`FALSCH` Wert wird automatisch verwendet beim Speichern in PDF/A und PDF/UA.

Core-Fonts werden beim Speichern im PDF 2.0-Format nicht unterstützt.`FALSCH`value wird used automatisch beim Speichern in PDF 2.0.

Diese Option hat dann eine höhere Priorität[`FontEmbeddingMode`](../fontembeddingmode/) Möglichkeit.

### Beispiele

Zeigt, wie die PDF Type 1-Schriftartersetzung aktiviert/deaktiviert wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Courier New";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

// Erstellen Sie ein "PdfSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
// um zu ändern, wie diese Methode das Dokument in .PDF konvertiert.
PdfSaveOptions options = new PdfSaveOptions();

// Setzen Sie die Eigenschaft "UseCoreFonts" auf "true", um einige Schriftarten zu ersetzen,
// einschließlich der beiden Schriftarten in unserem Dokument mit ihren PDF Type 1-Äquivalenten.
// Legen Sie die Eigenschaft "UseCoreFonts" auf "false" fest, um keine PDF Type 1-Schriftarten anzuwenden.
options.UseCoreFonts = useCoreFonts;

doc.Save(ArtifactsDir + "PdfSaveOptions.EmbedCoreFonts.pdf", options);

if (useCoreFonts)
    Assert.That(3000, Is.AtLeast(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedCoreFonts.pdf").Length));
else
    Assert.That(30000, Is.LessThan(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedCoreFonts.pdf").Length));
```

### Siehe auch

* class [PdfSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../pdfsaveoptions/)
* Montage [Aspose.Words](../../../)


