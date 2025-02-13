---
title: PdfSaveOptions.PageMode
second_title: Aspose.Words für .NET-API-Referenz
description: PdfSaveOptions eigendom. Gibt an wie das PDFDokument angezeigt werden soll wenn es im PDFReader geöffnet wird.
type: docs
weight: 220
url: /de/net/aspose.words.saving/pdfsaveoptions/pagemode/
---
## PdfSaveOptions.PageMode property

Gibt an, wie das PDF-Dokument angezeigt werden soll, wenn es im PDF-Reader geöffnet wird.

```csharp
public PdfPageMode PageMode { get; set; }
```

### Bemerkungen

Der Standardwert istUseOutlines .

### Beispiele

Zeigt, wie Sie Anweisungen festlegen, denen einige PDF-Reader beim Öffnen eines Ausgabedokuments folgen sollen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Erstellen Sie ein "PdfSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
// um zu ändern, wie diese Methode das Dokument in .PDF konvertiert.
PdfSaveOptions options = new PdfSaveOptions();

// Legen Sie die Eigenschaft "PageMode" auf "PdfPageMode.FullScreen" fest, damit der PDF-Reader die gespeicherte Datei öffnet
// Dokument im Vollbildmodus, der die Anzeige des Monitors übernimmt und keine Steuerelemente sichtbar hat.
// Legen Sie die Eigenschaft "PageMode" auf "PdfPageMode.UseThumbs" fest, damit der PDF-Reader ein separates Panel anzeigt
// mit einem Thumbnail für jede Seite im Dokument.
// Setzen Sie die Eigenschaft "PageMode" auf "PdfPageMode.UseOC", damit der PDF-Reader ein separates Panel anzeigt
// die es uns ermöglicht, mit allen im Dokument vorhandenen Ebenen zu arbeiten.
// Legen Sie die Eigenschaft "PageMode" auf "PdfPageMode.UseOutlines" fest, um den PDF-Reader zu erhalten
// auch um den Umriss anzuzeigen, wenn möglich.
// Setzen Sie die Eigenschaft "PageMode" auf "PdfPageMode.UseNone", damit der PDF-Reader nur das Dokument selbst anzeigt.
// Legen Sie die Eigenschaft "PageMode" auf "PdfPageMode.UseAttachments" fest, um das Bedienfeld für Anhänge sichtbar zu machen.
options.PageMode = pageMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.PageMode.pdf", options);
```

Zeigt die Verarbeitung von Lesezeichen in Kopf-/Fußzeilen in einem Dokument an, das wir in PDF rendern.

```csharp
Document doc = new Document(MyDir + "Bookmarks in headers and footers.docx");

// Erstellen Sie ein "PdfSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
// um zu ändern, wie diese Methode das Dokument in .PDF konvertiert.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Legen Sie die Eigenschaft „PageMode“ auf „PdfPageMode.UseOutlines“ fest, um den Gliederungsnavigationsbereich in der Ausgabe-PDF anzuzeigen.
saveOptions.PageMode = PdfPageMode.UseOutlines;

// Setzen Sie die Eigenschaft "DefaultBookmarksOutlineLevel" auf "1", um alles anzuzeigen
// Lesezeichen auf der ersten Gliederungsebene im Ausgabe-PDF.
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;

// Legen Sie die Eigenschaft "HeaderFooterBookmarksExportMode" auf "HeaderFooterBookmarksExportMode.None" fest
// keine Lesezeichen exportieren, die sich in Kopf-/Fußzeilen befinden.
// Legen Sie die Eigenschaft "HeaderFooterBookmarksExportMode" auf "HeaderFooterBookmarksExportMode.First" fest
// Lesezeichen nur in den Kopf-/Fußzeilen des ersten Abschnitts exportieren.
// Legen Sie die Eigenschaft "HeaderFooterBookmarksExportMode" auf "HeaderFooterBookmarksExportMode.All" fest
// Lesezeichen exportieren, die sich in allen Kopf-/Fußzeilen befinden.
saveOptions.HeaderFooterBookmarksExportMode = headerFooterBookmarksExportMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.HeaderFooterBookmarksExportMode.pdf", saveOptions);
```

### Siehe auch

* enum [PdfPageMode](../../pdfpagemode/)
* class [PdfSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../pdfsaveoptions/)
* Montage [Aspose.Words](../../../)


