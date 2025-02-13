---
title: Enum TxtExportHeadersFootersMode
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Saving.TxtExportHeadersFootersMode opsomming. Gibt an wie Kopf und Fußzeilen in das NurTextFormat exportiert werden.
type: docs
weight: 5360
url: /de/net/aspose.words.saving/txtexportheadersfootersmode/
---
## TxtExportHeadersFootersMode enumeration

Gibt an, wie Kopf- und Fußzeilen in das Nur-Text-Format exportiert werden.

```csharp
public enum TxtExportHeadersFootersMode
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| None | `0` | Es werden keine Kopf- und Fußzeilen exportiert. |
| PrimaryOnly | `1` | Nur primäre Kopf- und Fußzeilen werden am Anfang und Ende jedes Abschnitts exportiert. |
| AllAtEnd | `2` | Alle Kopf- und Fußzeilen werden nach allen Abschnittskörpern ganz am Ende eines Dokuments platziert. |

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

* namensraum [Aspose.Words.Saving](../../aspose.words.saving/)
* Montage [Aspose.Words](../../)


