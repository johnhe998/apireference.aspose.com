---
title: HtmlSaveOptions.MetafileFormat
second_title: Aspose.Words für .NET-API-Referenz
description: HtmlSaveOptions eigendom. Gibt an in welchem Format Metadateien gespeichert werden wenn sie in HTML MHTML oder EPUB exportiert werden. Standardwert istPng  was bedeutet dass Metadateien in RasterPNGBilder gerendert werden.
type: docs
weight: 390
url: /de/net/aspose.words.saving/htmlsaveoptions/metafileformat/
---
## HtmlSaveOptions.MetafileFormat property

Gibt an, in welchem Format Metadateien gespeichert werden, wenn sie in HTML, MHTML oder EPUB exportiert werden. Standardwert istPng , was bedeutet, dass Metadateien in Raster-PNG-Bilder gerendert werden.

```csharp
public HtmlMetafileFormat MetafileFormat { get; set; }
```

### Bemerkungen

Metadateien werden von HTML-Browsern nicht nativ angezeigt. Standardmäßig konvertiert Aspose.Words beim Exportieren in HTML WMF- und EMF- -Bilder in PNG-Dateien. Andere Optionen bestehen darin, Metadateien in SVG-Bilder zu konvertieren oder sie unverändert ohne Konvertierung zu exportieren .

Einige Bildtransformationen, insbesondere das Zuschneiden von Bildern, werden nicht auf Metafile-Bilder angewendet, wenn sie ohne Konvertierung in HTML exportiert werden.

### Beispiele

Zeigt, wie SVG-Objekte beim Speichern von HTML-Dokumenten in ein anderes Format konvertiert werden.

```csharp
string html = 
    @"<html>
        <svg xmlns='http://www.w3.org/2000/svg' width='500' height='40' viewBox='0 0 500 40'>
            <text x='0' y='35' font-family='Verdana' font-size='35'>Hello world!</text>
        </svg>
    </html>";

// Verwenden Sie 'ConvertSvgToEmf', um das Legacy-Verhalten umzukehren
// wo alle aus einem HTML-Dokument geladenen SVG-Bilder in EMF konvertiert wurden.
// Jetzt werden SVG-Bilder ohne Konvertierung geladen
// wenn die in den Ladeoptionen angegebene MS Word-Version SVG-Bilder nativ unterstützt.
HtmlLoadOptions loadOptions = new HtmlLoadOptions { ConvertSvgToEmf = true };

Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

// Dieses Dokument enthält ein <svg> Element in Form von Text.
// Wenn wir das Dokument im HTML-Format speichern, können wir ein SaveOptions-Objekt übergeben
// um zu bestimmen, wie die Speicheroperation dieses Objekt handhabt.
// Festlegen der Eigenschaft "MetafileFormat" auf "HtmlMetafileFormat.Png", um es in ein PNG-Bild zu konvertieren.
// Wenn Sie die Eigenschaft "MetafileFormat" auf "HtmlMetafileFormat.Svg" setzen, bleibt es als SVG-Objekt erhalten.
// Festlegen der Eigenschaft "MetafileFormat" auf "HtmlMetafileFormat.EmfOrWmf", um sie in eine Metadatei zu konvertieren.
HtmlSaveOptions options = new HtmlSaveOptions { MetafileFormat = htmlMetafileFormat };

doc.Save(ArtifactsDir + "HtmlSaveOptions.MetafileFormat.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.MetafileFormat.html");

switch (htmlMetafileFormat)
{
    case HtmlMetafileFormat.Png:
        Assert.True(outDocContents.Contains(
            "<p style=\"margin-top:0pt; margin-bottom:0pt\">" +
                "<img src=\"HtmlSaveOptions.MetafileFormat.001.png\" width=\"500\" height=\"40\" alt=\"\" " +
                "style=\"-aw-left-pos:0pt; -aw-rel-hpos:column; -aw-rel-vpos:paragraph; -aw-top-pos:0pt; -aw-wrap-type:inline\" />" +
            "</p>"));
        break;
    case HtmlMetafileFormat.Svg:
        Assert.True(outDocContents.Contains(
            "<span style=\"-aw-left-pos:0pt; -aw-rel-hpos:column; -aw-rel-vpos:paragraph; -aw-top-pos:0pt; -aw-wrap-type:inline\">" +
            "<svg xmlns=\"http://www.w3.org/2000/svg\" xmlns:xlink=\"http://www.w3.org/1999/xlink\" version=\"1.1\" width=\"499\" height= \"40\">"));
        break;
    case HtmlMetafileFormat.EmfOrWmf:
        Assert.True(outDocContents.Contains(
            "<p style=\"margin-top:0pt; margin-bottom:0pt\">" +
                "<img src=\"HtmlSaveOptions.MetafileFormat.001.emf\" width=\"500\" height=\"40\" alt=\"\" " +
                "style=\"-aw-left-pos:0pt; -aw-rel-hpos:column; -aw-rel-vpos:paragraph; -aw-top-pos:0pt; -aw-wrap-type:inline\" />" +
            "</p>"));
        break;
}
```

### Siehe auch

* property [ImageResolution](../imageresolution/)
* property [ScaleImageToShapeSize](../scaleimagetoshapesize/)
* enum [HtmlMetafileFormat](../../htmlmetafileformat/)
* class [HtmlSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../htmlsaveoptions/)
* Montage [Aspose.Words](../../../)


