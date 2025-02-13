---
title: HtmlFixedSaveOptions.ExportEmbeddedCss
second_title: Aspose.Words für .NET-API-Referenz
description: HtmlFixedSaveOptions eigendom. Gibt an ob das CSS Cascading Style Sheet in das HTMLDokument eingebettet werden soll.
type: docs
weight: 40
url: /de/net/aspose.words.saving/htmlfixedsaveoptions/exportembeddedcss/
---
## HtmlFixedSaveOptions.ExportEmbeddedCss property

Gibt an, ob das CSS (Cascading Style Sheet) in das HTML-Dokument eingebettet werden soll.

```csharp
public bool ExportEmbeddedCss { get; set; }
```

### Beispiele

Zeigt, wie Sie bestimmen, wo CSS-Stylesheets gespeichert werden, wenn Sie ein Dokument in HTML exportieren.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Wenn wir ein Dokument in HTML exportieren, erstellt Aspose.Words auch ein CSS-Stylesheet, um das Dokument damit zu formatieren.
// Wenn Sie das Flag "ExportEmbeddedCss" auf "true" setzen, speichern Sie das CSS-Stylesheet in einer .css-Datei,
// und mit einem <link> aus dem HTML-Dokument auf die Datei verlinken Element.
// Wenn das Flag auf "false" gesetzt wird, wird das CSS-Stylesheet in das HTML-Dokument eingebettet,
// Dadurch wird nur eine Datei anstelle von zwei erstellt.
HtmlFixedSaveOptions htmlFixedSaveOptions = new HtmlFixedSaveOptions
{
    ExportEmbeddedCss = exportEmbeddedCss
};

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedCss.html", htmlFixedSaveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedCss.html");

if (exportEmbeddedCss)
{
    Assert.True(Regex.Match(outDocContents, "<style type=\"text/css\">").Success);
    Assert.False(File.Exists(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedCss/styles.css"));
}
else
{
    Assert.True(Regex.Match(outDocContents,
        "<link rel=\"stylesheet\" type=\"text/css\" href=\"HtmlFixedSaveOptions[.]ExportEmbeddedCss/styles[.]css\" media=\"all\" />").Success);
    Assert.True(File.Exists(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedCss/styles.css"));
}
```

### Siehe auch

* class [HtmlFixedSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* Montage [Aspose.Words](../../../)


