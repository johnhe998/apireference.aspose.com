---
title: Document.AutomaticallyUpdateStyles
second_title: Aspose.Words per .NET API Reference
description: Document proprietà. Ottiene o imposta un flag che indica se gli stili nel documento vengono aggiornati per corrispondere agli stili nel modello allegato ogni volta che il documento viene aperto in MS Word.
type: docs
weight: 30
url: /it/net/aspose.words/document/automaticallyupdatestyles/
---
## Document.AutomaticallyUpdateStyles property

Ottiene o imposta un flag che indica se gli stili nel documento vengono aggiornati per corrispondere agli stili nel modello allegato ogni volta che il documento viene aperto in MS Word.

```csharp
public bool AutomaticallyUpdateStyles { get; set; }
```

### Esempi

Mostra come allegare un modello a un documento.

```csharp
Document doc = new Document();

// I documenti Microsoft Word vengono forniti per impostazione predefinita con un modello allegato chiamato "Normal.dotm".
// Non esiste un modello predefinito per i documenti Aspose.Words vuoti.
Assert.AreEqual(string.Empty, doc.AttachedTemplate);

// Allega un modello, quindi imposta il flag per applicare le modifiche allo stile
// all'interno del modello agli stili nel nostro documento.
doc.AttachedTemplate = MyDir + "Business brochure.dotx";
doc.AutomaticallyUpdateStyles = true;

doc.Save(ArtifactsDir + "Document.AutomaticallyUpdateStyles.docx");
```

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

* class [Document](../)
* spazio dei nomi [Aspose.Words](../../document/)
* assemblea [Aspose.Words](../../../)


