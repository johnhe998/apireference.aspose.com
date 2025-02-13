---
title: SaveOptions.DefaultTemplate
second_title: Aspose.Words per .NET API Reference
description: SaveOptions proprietà. Ottiene o imposta il percorso del modello predefinito incluso il nome file. Il valore predefinito per questa proprietà è stringa vuota Empty .
type: docs
weight: 40
url: /it/net/aspose.words.saving/saveoptions/defaulttemplate/
---
## SaveOptions.DefaultTemplate property

Ottiene o imposta il percorso del modello predefinito (incluso il nome file). Il valore predefinito per questa proprietà è **stringa vuota** (Empty ).

```csharp
public string DefaultTemplate { get; set; }
```

### Osservazioni

Se specificato, questo percorso viene utilizzato per caricare il modello quando[`AutomaticallyUpdateStyles`](../../../aspose.words/document/automaticallyupdatestyles/) è vero, ma[`AttachedTemplate`](../../../aspose.words/document/attachedtemplate/) è vuoto.

### Esempi

Mostra come impostare un modello predefinito per i documenti che non hanno modelli allegati.

```csharp
Document doc = new Document();

// Abilita l'aggiornamento automatico dello stile, ma non allega un documento modello.
doc.AutomaticallyUpdateStyles = true;

Assert.AreEqual(string.Empty, doc.AttachedTemplate);

// Poiché non esiste un documento modello, il documento non aveva un punto in cui tenere traccia delle modifiche allo stile.
// Usa un oggetto SaveOptions per impostare automaticamente un modello
// se un documento che stiamo salvando non ne ha uno.
SaveOptions options = SaveOptions.CreateSaveOptions("Document.DefaultTemplate.docx");
options.DefaultTemplate = MyDir + "Business brochure.dotx";

doc.Save(ArtifactsDir + "Document.DefaultTemplate.docx", options);
```

### Guarda anche

* class [SaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../saveoptions/)
* assemblea [Aspose.Words](../../../)


