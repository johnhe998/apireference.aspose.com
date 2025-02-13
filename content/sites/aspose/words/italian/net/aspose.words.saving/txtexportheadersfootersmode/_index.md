---
title: Enum TxtExportHeadersFootersMode
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Saving.TxtExportHeadersFootersMode enum. Specifica il modo in cui le intestazioni e i piè di pagina vengono esportati in formato testo normale.
type: docs
weight: 5360
url: /it/net/aspose.words.saving/txtexportheadersfootersmode/
---
## TxtExportHeadersFootersMode enumeration

Specifica il modo in cui le intestazioni e i piè di pagina vengono esportati in formato testo normale.

```csharp
public enum TxtExportHeadersFootersMode
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| None | `0` | Non vengono esportate intestazioni e piè di pagina. |
| PrimaryOnly | `1` | Solo le intestazioni e i piè di pagina primari vengono esportati all'inizio e alla fine di ogni sezione. |
| AllAtEnd | `2` | Tutte le intestazioni e i piè di pagina vengono posizionati dopo tutti i corpi delle sezioni alla fine di un documento. |

### Esempi

Mostra come specificare come esportare intestazioni e piè di pagina in formato testo normale.

```csharp
Document doc = new Document();

// Inserisce intestazioni/piè di pagina pari e primari nel documento.
// L'intestazione/piè di pagina principale sovrascriverà le intestazioni/piè di pagina pari.
doc.FirstSection.HeadersFooters.Add(new HeaderFooter(doc, HeaderFooterType.HeaderEven));
doc.FirstSection.HeadersFooters[HeaderFooterType.HeaderEven].AppendParagraph("Even header");
doc.FirstSection.HeadersFooters.Add(new HeaderFooter(doc, HeaderFooterType.FooterEven));
doc.FirstSection.HeadersFooters[HeaderFooterType.FooterEven].AppendParagraph("Even footer");
doc.FirstSection.HeadersFooters.Add(new HeaderFooter(doc, HeaderFooterType.HeaderPrimary));
doc.FirstSection.HeadersFooters[HeaderFooterType.HeaderPrimary].AppendParagraph("Primary header");
doc.FirstSection.HeadersFooters.Add(new HeaderFooter(doc, HeaderFooterType.FooterPrimary));
doc.FirstSection.HeadersFooters[HeaderFooterType.FooterPrimary].AppendParagraph("Primary footer");

// Inserisci pagine per visualizzare queste intestazioni e piè di pagina.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Page 1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 2");
builder.InsertBreak(BreakType.PageBreak); 
builder.Write("Page 3");

// Crea un oggetto "TxtSaveOptions", che possiamo passare al metodo "Save" del documento
// per modificare il modo in cui salviamo il documento come testo normale.
TxtSaveOptions saveOptions = new TxtSaveOptions();

// Imposta la proprietà "ExportHeadersFootersMode" su "TxtExportHeadersFootersMode.None"
// per non esportare intestazioni/piè di pagina.
// Imposta la proprietà "ExportHeadersFootersMode" su "TxtExportHeadersFootersMode.PrimaryOnly"
// per esportare solo intestazioni/piè di pagina primari.
// Imposta la proprietà "ExportHeadersFootersMode" su "TxtExportHeadersFootersMode.AllAtEnd"
// per posizionare tutte le intestazioni e i piè di pagina per tutti i corpi delle sezioni alla fine del documento.
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

### Guarda anche

* spazio dei nomi [Aspose.Words.Saving](../../aspose.words.saving/)
* assemblea [Aspose.Words](../../)


