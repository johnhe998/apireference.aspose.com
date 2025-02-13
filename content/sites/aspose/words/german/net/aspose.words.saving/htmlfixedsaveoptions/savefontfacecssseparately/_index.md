---
title: HtmlFixedSaveOptions.SaveFontFaceCssSeparately
second_title: Aspose.Words für .NET-API-Referenz
description: HtmlFixedSaveOptions eigendom. Flag gibt an ob fontfaceCSSRegeln in einer separaten Datei fontFaces.css abgelegt werden sollen wenn ein Dokument mit externem Stylesheet gespeichert wird d.h. wennExportEmbeddedCss istFALSCH . Standardwert istFALSCH  alle CSSRegeln werden in eine einzige Datei styles.css. geschrieben
type: docs
weight: 160
url: /de/net/aspose.words.saving/htmlfixedsaveoptions/savefontfacecssseparately/
---
## HtmlFixedSaveOptions.SaveFontFaceCssSeparately property

Flag gibt an, ob "@font-face"-CSS-Regeln in einer separaten Datei "fontFaces.css" abgelegt werden sollen, wenn ein Dokument mit externem Stylesheet gespeichert wird (d.h. wenn[`ExportEmbeddedCss`](../exportembeddedcss/) ist`FALSCH` ). Standardwert ist`FALSCH` , alle CSS-Regeln werden in eine einzige Datei "styles.css". geschrieben

```csharp
public bool SaveFontFaceCssSeparately { get; set; }
```

### Bemerkungen

Setzen dieser Eigenschaft auf`Stimmt` stellt das alte Verhalten (separate Dateien) für die Kompatibilität mit Legacy-Code wieder her.

### Beispiele

Zeigt, wie CSS in einer separaten Datei platziert und allen CSS-Klassennamen ein Präfix hinzugefügt wird.

```csharp
Document doc = new Document(MyDir + "Bookmarks.docx");

HtmlFixedSaveOptions htmlFixedSaveOptions = new HtmlFixedSaveOptions
{
    CssClassNamesPrefix = "myprefix",
    SaveFontFaceCssSeparately = true
};

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.AddCssClassNamesPrefix.html", htmlFixedSaveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlFixedSaveOptions.AddCssClassNamesPrefix.html");

Assert.True(Regex.Match(outDocContents,
    "<div class=\"myprefixdiv myprefixpage\" style=\"width:595[.]3pt; height:841[.]9pt;\">" +
    "<div class=\"myprefixdiv\" style=\"left:85[.]05pt; top:36pt; clip:rect[(]0pt,510[.]25pt,74[.]95pt,-85.05pt[)];\">" +
    "<span class=\"myprefixspan myprefixtext001\" style=\"font-size:11pt; left:294[.]73pt; top:0[.]36pt; line-height:12[.]29pt;\">").Success);

outDocContents = File.ReadAllText(ArtifactsDir + "HtmlFixedSaveOptions.AddCssClassNamesPrefix/styles.css");

Assert.True(Regex.Match(outDocContents,
    ".myprefixdiv { position:absolute; } " +
    ".myprefixspan { position:absolute; white-space:pre; color:#000000; font-size:12pt; }").Success);
```

### Siehe auch

* class [HtmlFixedSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* Montage [Aspose.Words](../../../)


