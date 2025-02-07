---
title: PdfSaveOptions.ExportLanguageToSpanTag
second_title: Aspose.Words für .NET-API-Referenz
description: PdfSaveOptions eigendom. Ruft einen Wert ab oder legt einen Wert fest der bestimmt ob ein SpanTag in der Dokumentstruktur erstellt werden soll um die Textsprache zu exportieren.
type: docs
weight: 130
url: /de/net/aspose.words.saving/pdfsaveoptions/exportlanguagetospantag/
---
## PdfSaveOptions.ExportLanguageToSpanTag property

Ruft einen Wert ab oder legt einen Wert fest, der bestimmt, ob ein "Span"-Tag in der Dokumentstruktur erstellt werden soll, um die Textsprache zu exportieren.

```csharp
public bool ExportLanguageToSpanTag { get; set; }
```

### Bemerkungen

Standardwert ist`FALSCH` und das Attribut "Lang" wird an eine Sequenz mit markiertem Inhalt in einem Seiteninhaltsstrom angehängt.

Wenn der Wert ist`Stimmt` Das Tag „Span“ wird für den Text mit nicht standardmäßiger Sprache erstellt, und das Attribut „Lang“ wird an dieses Tag angehängt.

Dieser Wert wird ignoriert, wenn[`ExportDocumentStructure`](../exportdocumentstructure/) ist`FALSCH` .

### Beispiele

Zeigt, wie Sie in der Dokumentstruktur ein "Span"-Tag erstellen, um die Textsprache zu exportieren.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");
builder.Writeln("Hola mundo!");

PdfSaveOptions saveOptions = new PdfSaveOptions
{
    // Hinweis: Wenn "ExportDocumentStructure" falsch ist, wird "ExportLanguageToSpanTag" ignoriert.
    ExportDocumentStructure = true, ExportLanguageToSpanTag = true
};

doc.Save(ArtifactsDir + "PdfSaveOptions.ExportLanguageToSpanTag.pdf", saveOptions);
```

### Siehe auch

* class [PdfSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../pdfsaveoptions/)
* Montage [Aspose.Words](../../../)


