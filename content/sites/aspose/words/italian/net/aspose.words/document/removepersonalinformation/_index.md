---
title: Document.RemovePersonalInformation
second_title: Aspose.Words per .NET API Reference
description: Document proprietà. Ottiene o imposta un flag che indica che Microsoft Word rimuoverà tutte le informazioni utente da commenti revisioni e proprietà del documento al salvataggio del documento.
type: docs
weight: 320
url: /it/net/aspose.words/document/removepersonalinformation/
---
## Document.RemovePersonalInformation property

Ottiene o imposta un flag che indica che Microsoft Word rimuoverà tutte le informazioni utente da commenti, revisioni e proprietà del documento al salvataggio del documento.

```csharp
public bool RemovePersonalInformation { get; set; }
```

### Esempi

Mostra come abilitare la rimozione delle informazioni personali durante un salvataggio manuale.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserisce alcuni contenuti con informazioni personali.
doc.BuiltInDocumentProperties.Author = "John Doe";
doc.BuiltInDocumentProperties.Company = "Placeholder Inc.";

doc.StartTrackRevisions(doc.BuiltInDocumentProperties.Author, DateTime.Now);
builder.Write("Hello world!");
doc.StopTrackRevisions();

// Questo flag equivale a File -> Opzioni -> Centro protezione -> Impostazioni del Centro protezione... ->
// Opzioni sulla privacy -> "Rimuovi le informazioni personali dalle proprietà del file al salvataggio" in Microsoft Word.
doc.RemovePersonalInformation = saveWithoutPersonalInfo;

// Questa opzione non avrà effetto durante un'operazione di salvataggio eseguita utilizzando Aspose.Words.
// I dati personali verranno rimossi dal nostro documento con il flag impostato quando lo salviamo manualmente utilizzando Microsoft Word.
doc.Save(ArtifactsDir + "Document.RemovePersonalInformation.docx");
doc = new Document(ArtifactsDir + "Document.RemovePersonalInformation.docx");

Assert.AreEqual(saveWithoutPersonalInfo, doc.RemovePersonalInformation);
Assert.AreEqual("John Doe", doc.BuiltInDocumentProperties.Author);
Assert.AreEqual("Placeholder Inc.", doc.BuiltInDocumentProperties.Company);
Assert.AreEqual("John Doe", doc.Revisions[0].Author);
```

### Guarda anche

* class [Document](../)
* spazio dei nomi [Aspose.Words](../../document/)
* assemblea [Aspose.Words](../../../)


