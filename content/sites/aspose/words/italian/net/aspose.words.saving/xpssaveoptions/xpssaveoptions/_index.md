---
title: XpsSaveOptions.XpsSaveOptions
second_title: Aspose.Words per .NET API Reference
description: XpsSaveOptions costruttore. Inizializza una nuova istanza di questa classe che può essere utilizzata per salvare un documento nelXps formato.
type: docs
weight: 10
url: /it/net/aspose.words.saving/xpssaveoptions/xpssaveoptions/
---
## XpsSaveOptions() {#constructor}

Inizializza una nuova istanza di questa classe che può essere utilizzata per salvare un documento nelXps formato.

```csharp
public XpsSaveOptions()
```

### Esempi

Mostra come limitare il livello delle intestazioni che appariranno nella struttura di un documento XPS salvato.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserisce intestazioni che possono fungere da voci TOC di livello 1, 2 e poi 3.
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

Assert.True(builder.ParagraphFormat.IsHeading);

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 1.2.1");
builder.Writeln("Heading 1.2.2");

// Crea un oggetto "XpsSaveOptions" che possiamo passare al metodo "Save" del documento
// per modificare il modo in cui quel metodo converte il documento in .XPS.
XpsSaveOptions saveOptions = new XpsSaveOptions();

Assert.AreEqual(SaveFormat.Xps, saveOptions.SaveFormat);

// Il documento XPS di output conterrà uno schema, un sommario che elenca i titoli nel corpo del documento.
// Cliccando su una voce in questo schema ci porterà alla posizione della rispettiva intestazione.
// Imposta la proprietà "HeadingsOutlineLevels" su "2" per escludere tutte le intestazioni i cui livelli sono superiori a 2 dalla struttura.
// Le ultime due intestazioni che abbiamo inserito sopra non appariranno.
saveOptions.OutlineOptions.HeadingsOutlineLevels = 2;

doc.Save(ArtifactsDir + "XpsSaveOptions.OutlineLevels.xps", saveOptions);
```

### Guarda anche

* class [XpsSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../xpssaveoptions/)
* assemblea [Aspose.Words](../../../)

---

## XpsSaveOptions(SaveFormat) {#constructor_1}

Inizializza una nuova istanza di questa classe che può essere utilizzata per salvare un documento nelXps oOpenXps formato.

```csharp
public XpsSaveOptions(SaveFormat saveFormat)
```

### Esempi

Mostra come salvare un documento nel formato XPS sotto forma di piegatura a libro.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");

// Crea un oggetto "XpsSaveOptions" che possiamo passare al metodo "Save" del documento
// per modificare il modo in cui quel metodo converte il documento in .XPS.
XpsSaveOptions xpsOptions = new XpsSaveOptions(SaveFormat.Xps);

// Imposta la proprietà "UseBookFoldPrintingSettings" su "true" per disporre i contenuti
// nell'XPS di output in un modo che ci aiuti a usarlo per creare un opuscolo.
// Imposta la proprietà "UseBookFoldPrintingSettings" su "false" per eseguire il rendering dell'XPS normalmente.
xpsOptions.UseBookFoldPrintingSettings = renderTextAsBookFold;

// Se stiamo visualizzando il documento come un opuscolo, dobbiamo impostare "MultiplePages"
// proprietà degli oggetti di impostazione della pagina di tutte le sezioni in "MultiplePagesType.BookFoldPrinting".
if (renderTextAsBookFold)
    foreach (Section s in doc.Sections)
    {
        s.PageSetup.MultiplePages = MultiplePagesType.BookFoldPrinting;
    }

// Una volta stampato questo documento, possiamo trasformarlo in un opuscolo impilando le pagine
// per uscire dalla stampante e piegarsi al centro.
doc.Save(ArtifactsDir + "XpsSaveOptions.BookFold.xps", xpsOptions);
```

### Guarda anche

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [XpsSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../xpssaveoptions/)
* assemblea [Aspose.Words](../../../)


