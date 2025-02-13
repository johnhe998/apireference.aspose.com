---
title: Enum HtmlOfficeMathOutputMode
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Saving.HtmlOfficeMathOutputMode opsomming. Gibt an wie Aspose.Words OfficeMath in HTML MHTML und EPUB exportiert.
type: docs
weight: 4840
url: /de/net/aspose.words.saving/htmlofficemathoutputmode/
---
## HtmlOfficeMathOutputMode enumeration

Gibt an, wie Aspose.Words OfficeMath in HTML, MHTML und EPUB exportiert.

```csharp
public enum HtmlOfficeMathOutputMode
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| Image | `0` | OfficeMath wird als Bild in HTML konvertiert, das durch das &lt;img&gt;-Tag angegeben wird. |
| MathML | `1` | OfficeMath wird mit MathML in HTML konvertiert. |
| Text | `2` | OfficeMath wird als Abfolge von Läufen in HTML konvertiert, die durch &lt;span&gt;-Tags angegeben werden. |

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

* namensraum [Aspose.Words.Saving](../../aspose.words.saving/)
* Montage [Aspose.Words](../../)


