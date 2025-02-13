---
title: SaveOptions.AllowEmbeddingPostScriptFonts
second_title: Aspose.Words für .NET-API-Referenz
description: SaveOptions eigendom. Ruft einen booleschen Wert ab oder legt ihn fest der angibt ob das Einbetten von Schriftarten mit PostScriptKonturen zulässig ist wenn TrueTypeSchriftarten in ein Dokument eingebettet werden nachdem es gespeichert wurde. Der Standardwert ist FALSCH .
type: docs
weight: 20
url: /de/net/aspose.words.saving/saveoptions/allowembeddingpostscriptfonts/
---
## SaveOptions.AllowEmbeddingPostScriptFonts property

Ruft einen booleschen Wert ab oder legt ihn fest, der angibt, ob das Einbetten von Schriftarten mit PostScript-Konturen zulässig ist, wenn TrueType-Schriftarten in ein Dokument eingebettet werden, nachdem es gespeichert wurde. Der Standardwert ist **FALSCH** .

```csharp
public bool AllowEmbeddingPostScriptFonts { get; set; }
```

### Bemerkungen

Beachten Sie, dass Word keine PostScript-Schriftarten einbettet, aber Dokumente mit eingebetteten Schriftarten dieses Typs öffnen kann.

Diese Option funktioniert nur, wenn[`EmbedTrueTypeFonts`](../../../aspose.words.fonts/fontinfocollection/embedtruetypefonts/) der [`FontInfos`](../../../aspose.words/documentbase/fontinfos/) Eigenschaft eingestellt ist`Stimmt`.

### Beispiele

Zeigt, wie das Dokument mit PostScript-Schriftart gespeichert wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "PostScriptFont";
builder.Writeln("Some text with PostScript font.");

// Laden Sie die Schriftart mit PostScript, die im Dokument verwendet werden soll.
MemoryFontSource otf = new MemoryFontSource(File.ReadAllBytes(FontsDir + "AllegroOpen.otf"));
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] { otf });

// TrueType-Schriftarten einbetten.
doc.FontInfos.EmbedTrueTypeFonts = true;

// Einbetten von PostScript-Fonts zulassen, während TrueType-Fonts eingebettet werden.
// Microsoft Word bettet keine PostScript-Schriftarten ein, kann aber Dokumente mit eingebetteten Schriftarten dieses Typs öffnen.
SaveOptions saveOptions = SaveOptions.CreateSaveOptions(SaveFormat.Docx);
saveOptions.AllowEmbeddingPostScriptFonts = true;

doc.Save(ArtifactsDir + "Document.AllowEmbeddingPostScriptFonts.docx", saveOptions);
```

### Siehe auch

* class [SaveOptions](../)
* namensraum [Aspose.Words.Saving](../../saveoptions/)
* Montage [Aspose.Words](../../../)


