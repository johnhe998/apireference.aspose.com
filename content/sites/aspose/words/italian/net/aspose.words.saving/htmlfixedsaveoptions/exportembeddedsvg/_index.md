---
title: HtmlFixedSaveOptions.ExportEmbeddedSvg
second_title: Aspose.Words per .NET API Reference
description: HtmlFixedSaveOptions proprietà. Specifica se le risorse SVG devono essere incorporate nel documento HTML. Il valore predefinito èVERO .
type: docs
weight: 70
url: /it/net/aspose.words.saving/htmlfixedsaveoptions/exportembeddedsvg/
---
## HtmlFixedSaveOptions.ExportEmbeddedSvg property

Specifica se le risorse SVG devono essere incorporate nel documento HTML. Il valore predefinito è`VERO` .

```csharp
public bool ExportEmbeddedSvg { get; set; }
```

### Esempi

Mostra come determinare dove archiviare gli oggetti SVG durante l'esportazione di un documento in Html.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// Quando esportiamo un documento con oggetti SVG in .html,
// Aspose.Words può posizionare questi oggetti in due possibili posizioni.
// L'impostazione del flag "ExportEmbeddedSvg" su "true" incorporerà tutti i dati grezzi degli oggetti SVG
// all'interno dell'HTML di output, all'interno di <image> tag.
// L'impostazione di questo flag su "false" creerà un file nel file system locale per ogni oggetto SVG.
// L'HTML si collegherà a ciascun file usando l'attributo "data" di un <object> etichetta.
HtmlFixedSaveOptions htmlFixedSaveOptions = new HtmlFixedSaveOptions
{
    ExportEmbeddedSvg = exportSvgs
};

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedSvgs.html", htmlFixedSaveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedSvgs.html");

if (exportSvgs)
{
    Assert.False(File.Exists(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedSvgs/svg001.svg"));
    Assert.True(Regex.Match(outDocContents,
        "<image id=\"image004\" xlink:href=.+/>").Success);
}
else
{
    Assert.True(File.Exists(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedSvgs/svg001.svg"));
    Assert.True(Regex.Match(outDocContents,
        "<object type=\"image/svg[+]xml\" data=\"HtmlFixedSaveOptions.ExportEmbeddedSvgs/svg001[.]svg\"></object>").Success);
}
```

### Guarda anche

* class [HtmlFixedSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* assemblea [Aspose.Words](../../../)


