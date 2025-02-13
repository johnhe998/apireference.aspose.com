---
title: HtmlSaveOptions.ExportCidUrlsForMhtmlResources
second_title: Aspose.Words per .NET API Reference
description: HtmlSaveOptions proprietà. Specifica se utilizzare gli URL CID ContentID per fare riferimento a risorse immagini caratteri CSS incluse nei documenti MHTML . Il valore predefinito èfalso .
type: docs
weight: 120
url: /it/net/aspose.words.saving/htmlsaveoptions/exportcidurlsformhtmlresources/
---
## HtmlSaveOptions.ExportCidUrlsForMhtmlResources property

Specifica se utilizzare gli URL CID (Content-ID) per fare riferimento a risorse (immagini, caratteri, CSS) incluse nei documenti MHTML . Il valore predefinito è`falso` .

```csharp
public bool ExportCidUrlsForMhtmlResources { get; set; }
```

### Osservazioni

Questa opzione ha effetto solo sui documenti salvati in MHTML.

Per impostazione predefinita, le risorse nei documenti MHTML sono referenziate dal nome del file (ad esempio, "image.png"), che viene confrontato con le intestazioni "Content-Location" delle parti MIME.

Questa opzione abilita un metodo alternativo, in cui i riferimenti ai file di risorse vengono scritti come URL CID (Content-ID) (ad esempio, "cid:image.png") e vengono confrontati con le intestazioni "Content-ID".

In teoria, non dovrebbero esserci differenze tra i due metodi di riferimento e uno di loro dovrebbe funzionare bene in qualsiasi browser o agente di posta. In pratica, tuttavia, alcuni agenti non riescono a recuperare le risorse in base al nome del file. Se il tuo browser o agente di posta si rifiuta di caricare le risorse incluse in un documento MTHML (non mostra le immagini o non carica gli stili CSS ), prova a esportare il documento con gli URL CID.

### Esempi

Mostra come abilitare gli ID contenuto per i documenti MHTML di output.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// L'impostazione di questo flag sostituirà i tag "Content-Location".
// con tag "Content-ID" per ogni risorsa dal documento di input.
HtmlSaveOptions options = new HtmlSaveOptions(SaveFormat.Mhtml)
{
    ExportCidUrlsForMhtmlResources = exportCidUrlsForMhtmlResources,
    CssStyleSheetType = CssStyleSheetType.External,
    ExportFontResources = true,
    PrettyFormat = true
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.ContentIdUrls.mht", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ContentIdUrls.mht");

if (exportCidUrlsForMhtmlResources)
{
    Assert.True(outDocContents.Contains("Content-ID: <document.html>"));
    Assert.True(outDocContents.Contains("<link href=3D\"cid:styles.css\" type=3D\"text/css\" rel=3D\"stylesheet\" />"));
    Assert.True(outDocContents.Contains("@font-face { font-family:'Arial Black'; font-weight:bold; src:url('cid:arib=\r\nlk.ttf') }"));
    Assert.True(outDocContents.Contains("<img src=3D\"cid:image.003.jpeg\" width=3D\"350\" height=3D\"180\" alt=3D\"\" />"));
}
else
{
    Assert.True(outDocContents.Contains("Content-Location: document.html"));
    Assert.True(outDocContents.Contains("<link href=3D\"styles.css\" type=3D\"text/css\" rel=3D\"stylesheet\" />"));
    Assert.True(outDocContents.Contains("@font-face { font-family:'Arial Black'; font-weight:bold; src:url('ariblk.t=\r\ntf') }"));
    Assert.True(outDocContents.Contains("<img src=3D\"image.003.jpeg\" width=3D\"350\" height=3D\"180\" alt=3D\"\" />"));
}
```

### Guarda anche

* class [HtmlSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../htmlsaveoptions/)
* assemblea [Aspose.Words](../../../)


