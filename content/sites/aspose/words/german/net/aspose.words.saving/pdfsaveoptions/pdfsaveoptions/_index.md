---
title: PdfSaveOptions.PdfSaveOptions
second_title: Aspose.Words für .NET-API-Referenz
description: PdfSaveOptions constructeur. Initialisiert eine neue Instanz dieser Klasse die zum Speichern eines Dokuments im verwendet werden kann.Pdf format.
type: docs
weight: 10
url: /de/net/aspose.words.saving/pdfsaveoptions/pdfsaveoptions/
---
## PdfSaveOptions constructor

Initialisiert eine neue Instanz dieser Klasse, die zum Speichern eines Dokuments im verwendet werden kann.Pdf format.

```csharp
public PdfSaveOptions()
```

### Beispiele

Zeigt, wie Untergruppen beim Einbetten von Schriftarten aktiviert oder deaktiviert werden, während ein Dokument in PDF gerendert wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Arvo";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

// Konfigurieren Sie unsere Schriftartquellen, um sicherzustellen, dass wir Zugriff auf beide Schriftarten in diesem Dokument haben.
FontSourceBase[] originalFontsSources = FontSettings.DefaultInstance.GetFontsSources();
Aspose.Words.Fonts.FolderFontSource folderFontSource = new Aspose.Words.Fonts.FolderFontSource(FontsDir, true);
FontSettings.DefaultInstance.SetFontsSources(new[] { originalFontsSources[0], folderFontSource });

FontSourceBase[] fontSources = FontSettings.DefaultInstance.GetFontsSources();
Assert.True(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));
Assert.True(fontSources[1].GetAvailableFonts().Any(f => f.FullFontName == "Arvo"));

// Erstellen Sie ein "PdfSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
// um zu ändern, wie diese Methode das Dokument in .PDF konvertiert.
PdfSaveOptions options = new PdfSaveOptions();

// Da unser Dokument eine benutzerdefinierte Schriftart enthält, kann eine Einbettung in das Ausgabedokument wünschenswert sein.
// Setzen Sie die Eigenschaft "EmbedFullFonts" auf "true", um jede Glyphe jeder eingebetteten Schriftart in die Ausgabe-PDF einzubetten.
// Die Größe des Dokuments kann sehr groß werden, aber wir können alle Schriftarten vollständig nutzen, wenn wir das PDF bearbeiten.
// Setzen Sie die Eigenschaft "EmbedFullFonts" auf "false", um Untergruppen auf Schriftarten anzuwenden und nur die Glyphen zu speichern
// die das Dokument verwendet. Die Datei wird erheblich kleiner,
// aber wir benötigen möglicherweise Zugriff auf benutzerdefinierte Schriftarten, wenn wir das Dokument bearbeiten.
options.EmbedFullFonts = embedFullFonts;

doc.Save(ArtifactsDir + "PdfSaveOptions.EmbedFullFonts.pdf", options);

if (embedFullFonts)
    Assert.That(500000, Is.LessThan(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedFullFonts.pdf").Length));
else
    Assert.That(25000, Is.AtLeast(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedFullFonts.pdf").Length));

// Stellen Sie die ursprünglichen Schriftartquellen wieder her.
FontSettings.DefaultInstance.SetFontsSources(originalFontsSources);
```

### Siehe auch

* class [PdfSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../pdfsaveoptions/)
* Montage [Aspose.Words](../../../)


