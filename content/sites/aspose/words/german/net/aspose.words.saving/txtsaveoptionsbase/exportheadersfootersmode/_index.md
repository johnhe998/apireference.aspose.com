---
title: TxtSaveOptionsBase.ExportHeadersFootersMode
second_title: Aspose.Words für .NET-API-Referenz
description: TxtSaveOptionsBase eigendom. Gibt an wie Kopf und Fußzeilen in die Textformate exportiert werden. Standardwert istPrimaryOnly .
type: docs
weight: 20
url: /de/net/aspose.words.saving/txtsaveoptionsbase/exportheadersfootersmode/
---
## TxtSaveOptionsBase.ExportHeadersFootersMode property

Gibt an, wie Kopf- und Fußzeilen in die Textformate exportiert werden. Standardwert istPrimaryOnly .

```csharp
public TxtExportHeadersFootersMode ExportHeadersFootersMode { get; set; }
```

### Beispiele

Zeigt, wie angegeben wird, wie Kopf- und Fußzeilen in das Nur-Text-Format exportiert werden.

```csharp
Document doc = new Document();

// Einfügen gerader und primärer Kopf-/Fußzeilen in das Dokument.
// Die primären Kopf-/Fußzeilen überschreiben die geraden Kopf-/Fußzeilen.
doc.FirstSection.HeadersFooters.Add(new HeaderFooter(doc, HeaderFooterType.HeaderEven));
doc.FirstSection.HeadersFooters[HeaderFooterType.HeaderEven].AppendParagraph("Even header");
doc.FirstSection.HeadersFooters.Add(new HeaderFooter(doc, HeaderFooterType.FooterEven));
doc.FirstSection.HeadersFooters[HeaderFooterType.FooterEven].AppendParagraph("Even footer");
doc.FirstSection.HeadersFooters.Add(new HeaderFooter(doc, HeaderFooterType.HeaderPrimary));
doc.FirstSection.HeadersFooters[HeaderFooterType.HeaderPrimary].AppendParagraph("Primary header");
doc.FirstSection.HeadersFooters.Add(new HeaderFooter(doc, HeaderFooterType.FooterPrimary));
doc.FirstSection.HeadersFooters[HeaderFooterType.FooterPrimary].AppendParagraph("Primary footer");

// Seiten einfügen, um diese Kopf- und Fußzeilen anzuzeigen.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Page 1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 2");
builder.InsertBreak(BreakType.PageBreak); 
builder.Write("Page 3");

// Erstellen Sie ein "TxtSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
// um zu ändern, wie wir das Dokument im Klartext speichern.
TxtSaveOptions saveOptions = new TxtSaveOptions();

// Setzen Sie die Eigenschaft "ExportHeadersFootersMode" auf "TxtExportHeadersFootersMode.None"
// keine Kopf-/Fußzeilen exportieren.
// Setzen Sie die Eigenschaft "ExportHeadersFootersMode" auf "TxtExportHeadersFootersMode.PrimaryOnly"
// um nur primäre Kopf-/Fußzeilen zu exportieren.
// Setzen Sie die Eigenschaft "ExportHeadersFootersMode" auf "TxtExportHeadersFootersMode.AllAtEnd"
// um alle Kopf- und Fußzeilen für alle Abschnittskörper am Ende des Dokuments zu platzieren.
saveOptions.ExportHeadersFootersMode = txtExportHeadersFootersMode;

doc.Save(ArtifactsDir + "TxtSaveOptions.ExportHeadersFooters.txt", saveOptions);

string docText = File.ReadAllText(ArtifactsDir + "TxtSaveOptions.ExportHeadersFooters.txt");

switch (txtExportHeadersFootersMode)
{
    case TxtExportHeadersFootersMode.AllAtEnd:
        Assert.AreEqual("Page 1\r\n" +
                        "Page 2\r\n" +
                        "Page 3\r\n" +
                        "Even header\r\n\r\n" +
                        "Primary header\r\n\r\n" +
                        "Even footer\r\n\r\n" +
                        "Primary footer\r\n\r\n", docText);
        break;
    case TxtExportHeadersFootersMode.PrimaryOnly:
        Assert.AreEqual("Primary header\r\n" +
                        "Page 1\r\n" +
                        "Page 2\r\n" +
                        "Page 3\r\n" +
                        "Primary footer\r\n", docText);
        break;
    case TxtExportHeadersFootersMode.None:
        Assert.AreEqual("Page 1\r\n" +
                        "Page 2\r\n" +
                        "Page 3\r\n", docText);
        break;
}
```

### Siehe auch

* enum [TxtExportHeadersFootersMode](../../txtexportheadersfootersmode/)
* class [TxtSaveOptionsBase](../)
* namensraum [Aspose.Words.Saving](../../txtsaveoptionsbase/)
* Montage [Aspose.Words](../../../)


