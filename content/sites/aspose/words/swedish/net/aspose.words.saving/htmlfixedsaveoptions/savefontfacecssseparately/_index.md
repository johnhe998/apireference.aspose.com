---
title: HtmlFixedSaveOptions.SaveFontFaceCssSeparately
second_title: Aspose.Words för .NET API Referens
description: HtmlFixedSaveOptions fast egendom. Flagga anger om fontface CSSregler ska placeras i en separat fil fontFaces.css när ett dokument sparas med extern stilmall det vill säga närExportEmbeddedCss ärfalsk . Standardvärdet ärfalsk  alla CSSregler skrivs i en enda fil styles.css.
type: docs
weight: 160
url: /sv/net/aspose.words.saving/htmlfixedsaveoptions/savefontfacecssseparately/
---
## HtmlFixedSaveOptions.SaveFontFaceCssSeparately property

Flagga anger om "@font-face" CSS-regler ska placeras i en separat fil "fontFaces.css" när ett dokument sparas med extern stilmall (det vill säga när[`ExportEmbeddedCss`](../exportembeddedcss/) är`falsk` ). Standardvärdet är`falsk` , alla CSS-regler skrivs i en enda fil "styles.css".

```csharp
public bool SaveFontFaceCssSeparately { get; set; }
```

### Anmärkningar

Ställer in den här egenskapen till`Sann` återställer det gamla beteendet (separata filer) för kompatibilitet med äldre kod.

### Exempel

Visar hur man placerar CSS i en separat fil och lägger till ett prefix till alla dess CSS-klassnamn.

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

### Se även

* class [HtmlFixedSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* hopsättning [Aspose.Words](../../../)


