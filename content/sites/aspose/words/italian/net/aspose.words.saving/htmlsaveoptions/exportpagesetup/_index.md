---
title: HtmlSaveOptions.ExportPageSetup
second_title: Aspose.Words per .NET API Reference
description: HtmlSaveOptions proprietà. Specifica se limpostazione della pagina viene esportata in HTML MHTML o EPUB. Limpostazione predefinita èfalso .
type: docs
weight: 230
url: /it/net/aspose.words.saving/htmlsaveoptions/exportpagesetup/
---
## HtmlSaveOptions.ExportPageSetup property

Specifica se l'impostazione della pagina viene esportata in HTML, MHTML o EPUB. L'impostazione predefinita è`falso` .

```csharp
public bool ExportPageSetup { get; set; }
```

### Osservazioni

A testa[`Section`](../../../aspose.words/section/) nel modello di documento Aspose.Words fornisce informazioni sull'impostazione della pagina tramite[`PageSetup`](../../../aspose.words/pagesetup/) classe. Quando esporti un documento in formato HTML, potrebbe essere necessario conservare queste informazioni per un ulteriore utilizzo. In particolare, l'impostazione della pagina potrebbe essere importante per il rendering su supporti impaginati (stampa) o la successiva conversione nei formati di file nativi di Microsoft Word (DOCX, DOC, RTF, WML).

Nella maggior parte dei casi l'HTML è destinato alla visualizzazione nei browser in cui non viene eseguita l'impaginazione. Quindi questa funzione è inattiva per impostazione predefinita.

### Esempi

Mostra come decidere se preservare la struttura della sezione/le informazioni sull'impostazione della pagina durante il salvataggio in HTML.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Section 1");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Section 2");

PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.TopMargin = 36.0;
pageSetup.BottomMargin = 36.0;
pageSetup.PaperSize = PaperSize.A5;

// Quando salviamo il documento in HTML, possiamo passare un oggetto SaveOptions
// per decidere se conservare o eliminare le impostazioni di configurazione della pagina.
// Se impostiamo il flag "ExportPageSetup" su "true", il documento HTML di output conterrà la nostra configurazione di configurazione della pagina.
// Se impostiamo il flag "ExportPageSetup" su "false", l'operazione di salvataggio annullerà le nostre impostazioni di configurazione della pagina
// per la prima sezione, ed entrambe le sezioni sembreranno identiche.
HtmlSaveOptions options = new HtmlSaveOptions { ExportPageSetup = exportPageSetup };

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportPageSetup.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ExportPageSetup.html");

if (exportPageSetup)
{
    Assert.True(outDocContents.Contains(
        "<style type=\"text/css\">" +
            "@page Section1 { size:419.55pt 595.3pt; margin:36pt 70.85pt }" +
            "@page Section2 { size:612pt 792pt; margin:70.85pt }" +
            "div.Section1 { page:Section1 }div.Section2 { page:Section2 }" +
        "</style>"));

    Assert.True(outDocContents.Contains(
        "<div class=\"Section1\">" +
            "<p style=\"margin-top:0pt; margin-bottom:0pt\">" +
                "<span>Section 1</span>" +
            "</p>" +
        "</div>"));
}
else
{
    Assert.False(outDocContents.Contains("style type=\"text/css\">"));

    Assert.True(outDocContents.Contains(
        "<div>" +
            "<p style=\"margin-top:0pt; margin-bottom:0pt\">" +
                "<span>Section 1</span>" +
            "</p>" +
        "</div>"));
}
```

### Guarda anche

* class [HtmlSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../htmlsaveoptions/)
* assemblea [Aspose.Words](../../../)


