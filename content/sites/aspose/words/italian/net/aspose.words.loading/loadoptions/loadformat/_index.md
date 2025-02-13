---
title: LoadOptions.LoadFormat
second_title: Aspose.Words per .NET API Reference
description: LoadOptions proprietà. Specifica il formato del documento da caricare. Il valore predefinito èAuto .
type: docs
weight: 90
url: /it/net/aspose.words.loading/loadoptions/loadformat/
---
## LoadOptions.LoadFormat property

Specifica il formato del documento da caricare. Il valore predefinito èAuto .

```csharp
public LoadFormat LoadFormat { get; set; }
```

### Osservazioni

Si consiglia di specificare ilAutovalue e lascia che Aspose.Words rilevi automaticamente il formato del file. Se conosci il formato del documento che stai per caricare, puoi specificare il formato in modo esplicito e questo ridurrà leggermente il tempo di caricamento dovuto all'overhead associato al rilevamento automatico del formato. Se specifichi un formato di caricamento esplicito, girerà per essere sbagliato, verrà invocato il rilevamento automatico e verrà effettuato un secondo tentativo di caricare il file.

### Esempi

Mostra come specificare un URI di base quando si apre un documento html.

```csharp
// Supponiamo di voler caricare un documento .html che contiene un'immagine collegata da un relativo URI
// mentre l'immagine si trova in una posizione diversa. In tal caso, dovremo risolvere l'URI relativo in uno assoluto.
 // Possiamo fornire un URI di base usando un oggetto HtmlLoadOptions.
HtmlLoadOptions loadOptions = new HtmlLoadOptions(LoadFormat.Html, "", ImageDir);

Assert.AreEqual(LoadFormat.Html, loadOptions.LoadFormat);

Document doc = new Document(MyDir + "Missing image.html", loadOptions);

// Mentre l'immagine era interrotta nell'input .html, il nostro URI di base personalizzato ci ha aiutato a riparare il collegamento.
Shape imageShape = (Shape)doc.GetChildNodes(NodeType.Shape, true)[0];
Assert.True(imageShape.IsImage);

// Questo documento di output mostrerà l'immagine mancante.
doc.Save(ArtifactsDir + "HtmlLoadOptions.BaseUri.docx");
```

### Guarda anche

* enum [LoadFormat](../../../aspose.words/loadformat/)
* class [LoadOptions](../)
* spazio dei nomi [Aspose.Words.Loading](../../loadoptions/)
* assemblea [Aspose.Words](../../../)


