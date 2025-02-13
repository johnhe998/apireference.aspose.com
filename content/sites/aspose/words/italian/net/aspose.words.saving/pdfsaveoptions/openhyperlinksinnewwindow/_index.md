---
title: PdfSaveOptions.OpenHyperlinksInNewWindow
second_title: Aspose.Words per .NET API Reference
description: PdfSaveOptions proprietà. Ottiene o imposta un valore che determina se i collegamenti ipertestuali nel Pdf di output document devono essere forzati per essere aperti in una nuova finestra o scheda di un browser.
type: docs
weight: 200
url: /it/net/aspose.words.saving/pdfsaveoptions/openhyperlinksinnewwindow/
---
## PdfSaveOptions.OpenHyperlinksInNewWindow property

Ottiene o imposta un valore che determina se i collegamenti ipertestuali nel Pdf di output document devono essere forzati per essere aperti in una nuova finestra (o scheda) di un browser.

```csharp
public bool OpenHyperlinksInNewWindow { get; set; }
```

### Osservazioni

Il valore predefinito è`falso` . Quando questo valore è impostato su`VERO` I collegamenti ipertestuali vengono salvati utilizzando il codice JavaScript. Il codice JavaScript è `app.launchURL("URL", vero);`, dove`URL` è un collegamento ipertestuale.

Si noti che se questa opzione è impostata su`VERO` i collegamenti ipertestuali non possono funzionare in alcuni lettori PDF, ad esempio Chrome, Firefox.

Le azioni JavaScript sono vietate dalla conformità PDF/A-1 e PDF/A-2.`falso` verrà utilizzato automaticamente durante il salvataggio di in PDF/A-1 e PDF/A-2.

### Esempi

Mostra come salvare i collegamenti ipertestuali in un documento che convertiamo in PDF in modo che aprano nuove pagine quando facciamo clic su di esse.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertHyperlink("Testlink", @"https://www.google.com/search?q=%20aspose", false);

// Crea un oggetto "PdfSaveOptions" che possiamo passare al metodo "Save" del documento
// per modificare il modo in cui quel metodo converte il documento in .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Imposta la proprietà "OpenHyperlinksInNewWindow" su "true" per salvare tutti i collegamenti ipertestuali usando il codice Javascript
// che obbliga i lettori ad aprire questi collegamenti in nuove finestre/schede del browser.
// Imposta la proprietà "OpenHyperlinksInNewWindow" su "false" per salvare normalmente tutti i collegamenti ipertestuali.
options.OpenHyperlinksInNewWindow = openHyperlinksInNewWindow;

doc.Save(ArtifactsDir + "PdfSaveOptions.OpenHyperlinksInNewWindow.pdf", options);
```

### Guarda anche

* class [PdfSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../pdfsaveoptions/)
* assemblea [Aspose.Words](../../../)


