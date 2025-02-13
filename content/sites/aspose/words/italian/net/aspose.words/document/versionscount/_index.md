---
title: Document.VersionsCount
second_title: Aspose.Words per .NET API Reference
description: Document proprietà. Ottiene il numero di versioni del documento archiviate nel documento DOC.
type: docs
weight: 440
url: /it/net/aspose.words/document/versionscount/
---
## Document.VersionsCount property

Ottiene il numero di versioni del documento archiviate nel documento DOC.

```csharp
public int VersionsCount { get; }
```

### Osservazioni

Le versioni in Microsoft Word sono accessibili tramite il menu File/Versioni. Microsoft Word supporta le versioni solo per i file DOC.

Questa proprietà consente di rilevare se c'erano versioni di documenti archiviate in questo documento prima che fosse aperto in Aspose.Words. Aspose.Words non fornisce altro supporto per le versioni del documento. Se si salva questo documento utilizzando Aspose.Words, il documento verrà salvato senza versioni.

### Esempi

Mostra come lavorare con la funzione di conteggio delle versioni dei documenti Microsoft Word meno recenti.

```csharp
Document doc = new Document(MyDir + "Versions.doc");

// Possiamo leggere questa proprietà di un documento, ma non possiamo conservarla durante il salvataggio.
Assert.AreEqual(4, doc.VersionsCount);

doc.Save(ArtifactsDir + "Document.VersionsCount.doc");      
doc = new Document(ArtifactsDir + "Document.VersionsCount.doc");

Assert.AreEqual(0, doc.VersionsCount);
```

### Guarda anche

* class [Document](../)
* spazio dei nomi [Aspose.Words](../../document/)
* assemblea [Aspose.Words](../../../)


