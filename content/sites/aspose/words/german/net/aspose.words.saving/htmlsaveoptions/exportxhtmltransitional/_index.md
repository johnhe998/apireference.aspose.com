---
title: HtmlSaveOptions.ExportXhtmlTransitional
second_title: Aspose.Words für .NET-API-Referenz
description: HtmlSaveOptions eigendom. Gibt an ob die DOCTYPEDeklaration beim Speichern in HTML oder MHTML geschrieben werden soll. WannStimmt  schreibt eine DOCTYPEDeklaration in das Dokument vor dem Wurzelelement. Standardwert istFALSCH. Beim Speichern in EPUB oder HTML5 Html5  wird immer die Deklaration DOCTYPE geschrieben.
type: docs
weight: 290
url: /de/net/aspose.words.saving/htmlsaveoptions/exportxhtmltransitional/
---
## HtmlSaveOptions.ExportXhtmlTransitional property

Gibt an, ob die DOCTYPE-Deklaration beim Speichern in HTML oder MHTML geschrieben werden soll. Wann`Stimmt` , schreibt eine DOCTYPE-Deklaration in das Dokument vor dem Wurzelelement. Standardwert ist`FALSCH`. Beim Speichern in EPUB oder HTML5 (Html5 ) wird immer die Deklaration DOCTYPE geschrieben.

```csharp
public bool ExportXhtmlTransitional { get; set; }
```

### Bemerkungen

Aspose.Words schreibt unabhängig von dieser Einstellung immer wohlgeformtes HTML.

Wann`Stimmt`, sieht der Anfang des HTML-Ausgabedokuments wie folgt aus:

Aspose.Words zielt darauf ab, XHTML gemäß der XHTML 1.0 Transitional-Spezifikation auszugeben, aber die Ausgabe wird nicht immer gegen die DTD validiert. Einige Strukturen in einem Microsoft Word -Dokument lassen sich nur schwer oder gar nicht einem Dokument zuordnen, das gegen das XHTML-Schema validiert wird. Zum Beispiel erlaubt XHTML keine verschachtelten Listen (UL kann nicht in ein anderes UL-Element verschachtelt werden), aber in Microsoft Word-Dokumenten kommen mehrstufige Listen ziemlich oft vor.

```csharp
<?xml version="1.0" encoding="utf-8" standalone="no" ?>
<!DOCTYPE html 
      PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en" lang="en">
```

### Beispiele

Zeigt, wie eine DOCTYPE-Überschrift angezeigt wird, wenn Dokumente in den Übergangsstandard Xhtml 1.0 konvertiert werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");

HtmlSaveOptions options = new HtmlSaveOptions(SaveFormat.Html)
{
    HtmlVersion = HtmlVersion.Xhtml,
    ExportXhtmlTransitional = showDoctypeDeclaration,
    PrettyFormat = true
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportXhtmlTransitional.html", options);

// Unser Dokument enthält nur dann eine DOCTYPE-Deklarationsüberschrift, wenn wir das Flag "ExportXhtmlTransitional" auf "true" gesetzt haben.
string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ExportXhtmlTransitional.html");

if (showDoctypeDeclaration)
    Assert.True(outDocContents.Contains(
        "<?xml version=\"1.0\" encoding=\"utf-8\" standalone=\"no\"?>\r\n" +
        "<!DOCTYPE html PUBLIC \"-//W3C//DTD XHTML 1.0 Transitional//EN\" \"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd\">\r\n" +
        "<html xmlns=\"http://www.w3.org/1999/xhtml\">"));
else
    Assert.True(outDocContents.Contains("<html>"));
```

### Siehe auch

* class [HtmlSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../htmlsaveoptions/)
* Montage [Aspose.Words](../../../)


