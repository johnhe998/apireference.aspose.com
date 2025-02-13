---
title: HtmlSaveOptions.ExportXhtmlTransitional
second_title: Aspose.Words per .NET API Reference
description: HtmlSaveOptions proprietà. Specifica se scrivere la dichiarazione DOCTYPE durante il salvataggio in HTML o MHTML. QuandoVERO  scrive una dichiarazione DOCTYPE nel documento prima dellelemento radice. Il valore predefinito èfalso. Quando si salva in EPUB o HTML5 Html5  viene sempre scritta la dichiarazione DOCTYPE .
type: docs
weight: 290
url: /it/net/aspose.words.saving/htmlsaveoptions/exportxhtmltransitional/
---
## HtmlSaveOptions.ExportXhtmlTransitional property

Specifica se scrivere la dichiarazione DOCTYPE durante il salvataggio in HTML o MHTML. Quando`VERO` , scrive una dichiarazione DOCTYPE nel documento prima dell'elemento radice. Il valore predefinito è`falso`. Quando si salva in EPUB o HTML5 (Html5 ) viene sempre scritta la dichiarazione DOCTYPE .

```csharp
public bool ExportXhtmlTransitional { get; set; }
```

### Osservazioni

Aspose.Words scrive sempre HTML ben formato indipendentemente da questa impostazione.

quando`VERO`, l'inizio del documento di output HTML sarà simile al seguente:

Aspose.Words mira a produrre XHTML secondo la specifica XHTML 1.0 Transitional, ma l'output non sarà sempre convalidato rispetto al DTD. Alcune strutture all'interno di un documento Microsoft Word sono difficili o impossibili da mappare a un documento che convaliderà lo schema XHTML. Ad esempio, XHTML non consente elenchi nidificati (UL non può essere nidificato all'interno di un altro elemento UL), ma nel documento Microsoft Word gli elenchi multilivello si verificano abbastanza spesso.

```csharp
<?xml version="1.0" encoding="utf-8" standalone="no" ?>
<!DOCTYPE html 
      PUBLIC "-//W3C//DTD XHTML 1.0 di transizione//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en" lang="it">
```

### Esempi

Mostra come visualizzare un'intestazione DOCTYPE durante la conversione di documenti nello standard di transizione Xhtml 1.0.

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

// Il nostro documento conterrà un'intestazione di dichiarazione DOCTYPE solo se abbiamo impostato il flag "ExportXhtmlTransitional" su "true".
string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ExportXhtmlTransitional.html");

if (showDoctypeDeclaration)
    Assert.True(outDocContents.Contains(
        "<?xml version=\"1.0\" encoding=\"utf-8\" standalone=\"no\"?>\r\n" +
        "<!DOCTYPE html PUBLIC \"-//W3C//DTD XHTML 1.0 Transitional//EN\" \"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd\">\r\n" +
        "<html xmlns=\"http://www.w3.org/1999/xhtml\">"));
else
    Assert.True(outDocContents.Contains("<html>"));
```

### Guarda anche

* class [HtmlSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../htmlsaveoptions/)
* assemblea [Aspose.Words](../../../)


