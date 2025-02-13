---
title: PdfSaveOptions.PreblendImages
second_title: Aspose.Words für .NET-API-Referenz
description: PdfSaveOptions eigendom. Ruft einen Wert ab oder legt einen Wert fest der bestimmt ob transparente Bilder mit schwarzer Hintergrundfarbe vorgemischt werden sollen oder nicht.
type: docs
weight: 230
url: /de/net/aspose.words.saving/pdfsaveoptions/preblendimages/
---
## PdfSaveOptions.PreblendImages property

Ruft einen Wert ab oder legt einen Wert fest, der bestimmt, ob transparente Bilder mit schwarzer Hintergrundfarbe vorgemischt werden sollen oder nicht.

```csharp
public bool PreblendImages { get; set; }
```

### Bemerkungen

Das Preblending von Bildern kann das visuelle Erscheinungsbild von PDF-Dokumenten in Adobe Reader verbessern und Anti-Aliasing-Artefakte entfernen.

Um vorgemischte Bilder richtig anzuzeigen, muss die PDF-Viewer-Anwendung den /Matte-Eintrag im Softmask-Bildwörterbuch unterstützen. Außerdem kann das Vormischen von Bildern die PDF-Rendering-Leistung beeinträchtigen.

Der Standardwert ist`FALSCH`.

### Beispiele

Zeigt, wie Bilder mit transparentem Hintergrund vorgemischt werden, während ein Dokument als PDF gespeichert wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Image img = Image.FromFile(ImageDir + "Transparent background logo.png");
builder.InsertImage(img);

// Erstellen Sie ein "PdfSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
// um zu ändern, wie diese Methode das Dokument in .PDF konvertiert.
PdfSaveOptions options = new PdfSaveOptions();

// Setzen Sie die Eigenschaft "PreblendImages" auf "true", um transparente Bilder vorzumischen
// mit einem Hintergrund, der Artefakte reduzieren kann.
// Setzen Sie die Eigenschaft "PreblendImages" auf "false", um transparente Bilder normal zu rendern.
options.PreblendImages = preblendImages;

doc.Save(ArtifactsDir + "PdfSaveOptions.PreblendImages.pdf", options);
```

Zeigt, wie Bilder mit transparentem Hintergrund (.NetStandard 2.0) vorgemischt werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (Image image = Image.Decode(ImageDir + "Transparent background logo.png"))
    builder.InsertImage(image);

// Erstellen Sie ein "PdfSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
// um zu ändern, wie diese Methode das Dokument in .PDF konvertiert.
PdfSaveOptions options = new PdfSaveOptions();

// Setzen Sie die Eigenschaft "PreblendImages" auf "true", um transparente Bilder vorzumischen
// mit einem Hintergrund, der Artefakte reduzieren kann.
// Setzen Sie die Eigenschaft "PreblendImages" auf "false", um transparente Bilder normal zu rendern.
options.PreblendImages = preblendImages;

doc.Save(ArtifactsDir + "PdfSaveOptions.PreblendImagesNetStandard2.pdf", options);
```

### Siehe auch

* class [PdfSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../pdfsaveoptions/)
* Montage [Aspose.Words](../../../)


