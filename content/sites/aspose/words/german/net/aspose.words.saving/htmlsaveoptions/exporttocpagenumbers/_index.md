---
title: HtmlSaveOptions.ExportTocPageNumbers
second_title: Aspose.Words für .NET-API-Referenz
description: HtmlSaveOptions eigendom. Gibt an ob beim Speichern von HTML MHTML und EPUB Seitenzahlen in das Inhaltsverzeichnis geschrieben werden sollen. Der Standardwert istFALSCH .
type: docs
weight: 280
url: /de/net/aspose.words.saving/htmlsaveoptions/exporttocpagenumbers/
---
## HtmlSaveOptions.ExportTocPageNumbers property

Gibt an, ob beim Speichern von HTML, MHTML und EPUB Seitenzahlen in das Inhaltsverzeichnis geschrieben werden sollen. Der Standardwert ist`FALSCH` .

```csharp
public bool ExportTocPageNumbers { get; set; }
```

### Beispiele

Zeigt, wie Seitenzahlen angezeigt werden, wenn ein Dokument mit einem Inhaltsverzeichnis in .html gespeichert wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ein Inhaltsverzeichnis einfügen und dann das Dokument mit Absätzen füllen, die mit einer "Überschrift" formatiert sind
// Stil, den das Inhaltsverzeichnis als Einträge aufnimmt. Bei jedem Eintrag wird links der Überschriftenabsatz angezeigt,
// und die Seitenzahl, die rechts die Überschrift enthält.
FieldToc fieldToc = (FieldToc)builder.InsertField(FieldType.FieldTOC, true);

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 1"];
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Entry 1");
builder.Writeln("Entry 2");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Entry 3");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Entry 4");
fieldToc.UpdatePageNumbers();
doc.UpdateFields();

// HTML-Dokumente haben keine Seiten. Wenn wir dieses Dokument in HTML speichern,
// Die Seitenzahlen, die unser Inhaltsverzeichnis anzeigt, haben keine Bedeutung.
// Wenn wir das Dokument im HTML-Format speichern, können wir ein SaveOptions-Objekt übergeben, um diese Seitenzahlen aus dem Inhaltsverzeichnis wegzulassen.
// Wenn wir das Flag "ExportTocPageNumbers" auf "true" setzen,
// jeder TOC-Eintrag zeigt die Überschrift, das Trennzeichen und die Seitennummer an, wobei sein Erscheinungsbild in Microsoft Word beibehalten wird.
// Wenn wir das Flag "ExportTocPageNumbers" auf "false" setzen,
// Die Speicheroperation lässt sowohl das Trennzeichen als auch die Seitenzahl weg und lässt die Überschrift für jeden Eintrag intakt.
HtmlSaveOptions options = new HtmlSaveOptions { ExportTocPageNumbers = exportTocPageNumbers };

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportTocPageNumbers.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ExportTocPageNumbers.html");

if (exportTocPageNumbers)
{
    Assert.True(outDocContents.Contains(
        "<p style=\"margin-top:0pt; margin-bottom:0pt\">" +
        "<span>Entry 1</span>" +
        "<span style=\"width:428.14pt; font-family:'Lucida Console'; font-size:10pt; display:inline-block; -aw-font-family:'Times New Roman'; " +
        "-aw-tabstop-align:right; -aw-tabstop-leader:dots; -aw-tabstop-pos:469.8pt\">.......................................................................</span>" +
        "<span>2</span>" +
        "</p>"));
}
else
{
    Assert.True(outDocContents.Contains(
        "<p style=\"margin-top:0pt; margin-bottom:0pt\">" +
        "<span>Entry 1</span>" +
        "</p>"));
}
```

### Siehe auch

* class [HtmlSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../htmlsaveoptions/)
* Montage [Aspose.Words](../../../)


