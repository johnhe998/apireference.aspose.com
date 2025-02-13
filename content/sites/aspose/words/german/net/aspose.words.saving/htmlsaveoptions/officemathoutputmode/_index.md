---
title: HtmlSaveOptions.OfficeMathOutputMode
second_title: Aspose.Words für .NET-API-Referenz
description: HtmlSaveOptions eigendom. Steuert wie OfficeMathObjekte in HTML MHTML oder EPUB exportiert werden. Standardwert istHtmlOfficeMathOutputMode.Image .
type: docs
weight: 400
url: /de/net/aspose.words.saving/htmlsaveoptions/officemathoutputmode/
---
## HtmlSaveOptions.OfficeMathOutputMode property

Steuert, wie OfficeMath-Objekte in HTML, MHTML oder EPUB exportiert werden. Standardwert ist`HtmlOfficeMathOutputMode.Image` .

```csharp
public HtmlOfficeMathOutputMode OfficeMathOutputMode { get; set; }
```

### Beispiele

Zeigt, wie angegeben wird, wie Microsoft OfficeMath-Objekte in HTML exportiert werden.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

// Wenn wir das Dokument im HTML-Format speichern, können wir ein SaveOptions-Objekt übergeben
// um zu bestimmen, wie der Speichervorgang OfficeMath-Objekte handhabt.
// Setzen der Eigenschaft "OfficeMathOutputMode" auf "HtmlOfficeMathOutputMode.Image"
// rendert jedes OfficeMath-Objekt in ein Bild.
// Setzen der Eigenschaft "OfficeMathOutputMode" auf "HtmlOfficeMathOutputMode.MathML"
// Konvertiert jedes OfficeMath-Objekt in MathML.
// Setzen der Eigenschaft "OfficeMathOutputMode" auf "HtmlOfficeMathOutputMode.Text"
// stellt jede OfficeMath-Formel mit einfachem HTML-Text dar.
HtmlSaveOptions options = new HtmlSaveOptions { OfficeMathOutputMode = htmlOfficeMathOutputMode };

doc.Save(ArtifactsDir + "HtmlSaveOptions.OfficeMathOutputMode.html", options);
string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.OfficeMathOutputMode.html");

switch (htmlOfficeMathOutputMode)
{
    case HtmlOfficeMathOutputMode.Image:
        Assert.True(Regex.Match(outDocContents, 
            "<p style=\"margin-top:0pt; margin-bottom:10pt\">" +
                "<img src=\"HtmlSaveOptions.OfficeMathOutputMode.001.png\" width=\"159\" height=\"19\" alt=\"\" style=\"vertical-align:middle; " +
                "-aw-left-pos:0pt; -aw-rel-hpos:column; -aw-rel-vpos:paragraph; -aw-top-pos:0pt; -aw-wrap-type:inline\" />" +
            "</p>").Success);
        break;
    case HtmlOfficeMathOutputMode.MathML:
        Assert.True(Regex.Match(outDocContents,
            "<p style=\"margin-top:0pt; margin-bottom:10pt; text-align:center\">" +
                "<math xmlns=\"http://www.w3.org/1998/Math/MathML\">" +
                    "<mi>i</mi>" +
                    "<mo>[+]</mo>" +
                    "<mi>b</mi>" +
                    "<mo>-</mo>" +
                    "<mi>c</mi>" +
                    "<mo>≥</mo>" +
                    ".*" +
                "</math>" +
            "</p>").Success);
        break;
    case HtmlOfficeMathOutputMode.Text:
        Assert.True(Regex.Match(outDocContents,
            @"<p style=\""margin-top:0pt; margin-bottom:10pt; text-align:center\"">" +
                @"<span style=\""font-family:'Cambria Math'\"">i[+]b-c≥iM[+]bM-cM </span>" +
            "</p>").Success);
        break;
}
```

### Siehe auch

* enum [HtmlOfficeMathOutputMode](../../htmlofficemathoutputmode/)
* class [HtmlSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../htmlsaveoptions/)
* Montage [Aspose.Words](../../../)


