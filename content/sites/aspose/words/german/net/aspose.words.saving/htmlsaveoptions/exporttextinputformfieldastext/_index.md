---
title: HtmlSaveOptions.ExportTextInputFormFieldAsText
second_title: Aspose.Words für .NET-API-Referenz
description: HtmlSaveOptions eigendom. Steuert wie Texteingabeformularfelder in HTML oder MHTML gespeichert werden. Standardwert istFALSCH .
type: docs
weight: 270
url: /de/net/aspose.words.saving/htmlsaveoptions/exporttextinputformfieldastext/
---
## HtmlSaveOptions.ExportTextInputFormFieldAsText property

Steuert, wie Texteingabeformularfelder in HTML oder MHTML gespeichert werden. Standardwert ist`FALSCH` .

```csharp
public bool ExportTextInputFormFieldAsText { get; set; }
```

### Bemerkungen

Wenn eingestellt auf`Stimmt` , exportiert Texteingabeformularfelder als normalen Text. Wann`FALSCH`, exportiert Word-Texteingabeformularfelder als INPUT-Elemente in HTML.

Beim Exportieren in EPUB werden Texteingabeformularfelder aufgrund der Anforderungen dieses Formats immer als Text gespeichert.

### Beispiele

Zeigt, wie der Ordner zum Speichern verknüpfter Bilder nach dem Speichern in .html angegeben wird.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

string imagesDir = Path.Combine(ArtifactsDir, "SaveHtmlWithOptions");

if (Directory.Exists(imagesDir))
    Directory.Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

// Legen Sie eine Option zum Exportieren von Formularfeldern als einfachen Text anstelle von HTML-Eingabeelementen fest.
HtmlSaveOptions options = new HtmlSaveOptions(SaveFormat.Html)
{
    ExportTextInputFormFieldAsText = true, 
    ImagesFolder = imagesDir
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.SaveHtmlWithOptions.html", options);
```

### Siehe auch

* class [HtmlSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../htmlsaveoptions/)
* Montage [Aspose.Words](../../../)


