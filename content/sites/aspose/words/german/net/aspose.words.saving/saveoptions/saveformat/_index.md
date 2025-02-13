---
title: SaveOptions.SaveFormat
second_title: Aspose.Words für .NET-API-Referenz
description: SaveOptions eigendom. Gibt das Format an in dem das Dokument gespeichert wird wenn dieses Speicheroptionsobjekt verwendet wird.
type: docs
weight: 140
url: /de/net/aspose.words.saving/saveoptions/saveformat/
---
## SaveOptions.SaveFormat property

Gibt das Format an, in dem das Dokument gespeichert wird, wenn dieses Speicheroptionsobjekt verwendet wird.

```csharp
public abstract SaveFormat SaveFormat { get; set; }
```

### Beispiele

Zeigt, wie Sie beim Speichern eines Dokuments im .epub-Format eine bestimmte Codierung verwenden.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Verwenden Sie ein SaveOptions-Objekt, um die Kodierung für ein zu speicherndes Dokument anzugeben.
HtmlSaveOptions saveOptions = new HtmlSaveOptions();
saveOptions.SaveFormat = SaveFormat.Epub;
saveOptions.Encoding = Encoding.UTF8;

// Standardmäßig hat ein ausgegebenes .epub-Dokument seinen gesamten Inhalt in einem HTML-Teil.
// Ein Split-Kriterium ermöglicht es uns, das Dokument in mehrere HTML-Teile zu segmentieren.
// Wir werden die Kriterien festlegen, um das Dokument in Überschriftenabsätze aufzuteilen.
// Dies ist nützlich für Leser, die keine HTML-Dateien lesen können, die größer als eine bestimmte Größe sind.
saveOptions.DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph;

// Geben Sie an, dass wir Dokumenteigenschaften exportieren möchten.
saveOptions.ExportDocumentProperties = true;

doc.Save(ArtifactsDir + "HtmlSaveOptions.Doc2EpubSaveOptions.epub", saveOptions);
```

### Siehe auch

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [SaveOptions](../)
* namensraum [Aspose.Words.Saving](../../saveoptions/)
* Montage [Aspose.Words](../../../)


