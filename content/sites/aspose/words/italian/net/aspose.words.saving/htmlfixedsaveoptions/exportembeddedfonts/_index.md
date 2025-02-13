---
title: HtmlFixedSaveOptions.ExportEmbeddedFonts
second_title: Aspose.Words per .NET API Reference
description: HtmlFixedSaveOptions proprietà. Specifica se i caratteri devono essere incorporati nel documento HTML in formato Base64. Nota limpostazione di questo flag può aumentare notevolmente le dimensioni del file HTML di output.
type: docs
weight: 50
url: /it/net/aspose.words.saving/htmlfixedsaveoptions/exportembeddedfonts/
---
## HtmlFixedSaveOptions.ExportEmbeddedFonts property

Specifica se i caratteri devono essere incorporati nel documento HTML in formato Base64. Nota l'impostazione di questo flag può aumentare notevolmente le dimensioni del file HTML di output.

```csharp
public bool ExportEmbeddedFonts { get; set; }
```

### Esempi

Mostra come determinare dove archiviare i caratteri incorporati durante l'esportazione di un documento in HTML.

```csharp
Document doc = new Document(MyDir + "Embedded font.docx");

// Quando esportiamo un documento con caratteri incorporati in .html,
// Aspose.Words può posizionare i caratteri in due possibili posizioni.
// L'impostazione del flag "ExportEmbeddedFonts" su "true" memorizzerà i dati grezzi per i caratteri incorporati all'interno del foglio di stile CSS,
// nella proprietà "url" della regola "@font-face". Questo potrebbe creare un enorme file di foglio di stile CSS
// e riduci il numero di file esterni che creerà questa conversione HTML.
// Impostando questo flag su "false" verrà creato un file per ogni font.
// Il foglio di stile CSS si collegherà a ciascun file di font utilizzando la proprietà "url" della regola "@font-face".
HtmlFixedSaveOptions htmlFixedSaveOptions = new HtmlFixedSaveOptions
{
    ExportEmbeddedFonts = exportEmbeddedFonts
};

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedFonts.html", htmlFixedSaveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedFonts/styles.css");

if (exportEmbeddedFonts)
{
    Assert.True(Regex.Match(outDocContents,
        "@font-face { font-family:'Arial'; font-style:normal; font-weight:normal; src:local[(]'☺'[)], url[(].+[)] format[(]'woff'[)]; }").Success);
    Assert.AreEqual(0, Directory.GetFiles(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedFonts").Count(f => f.EndsWith(".woff")));
}
else
{
    Assert.True(Regex.Match(outDocContents,
        "@font-face { font-family:'Arial'; font-style:normal; font-weight:normal; src:local[(]'☺'[)], url[(]'font001[.]woff'[)] format[(]'woff'[)]; }").Success);
    Assert.AreEqual(2, Directory.GetFiles(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedFonts").Count(f => f.EndsWith(".woff")));
}
```

### Guarda anche

* class [HtmlFixedSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* assemblea [Aspose.Words](../../../)


