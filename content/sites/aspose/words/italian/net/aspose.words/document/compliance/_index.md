---
title: Document.Compliance
second_title: Aspose.Words per .NET API Reference
description: Document proprietà. Ottiene la versione di conformità OOXML determinata dal contenuto del documento caricato. Ha senso solo per documenti OOXML.
type: docs
weight: 60
url: /it/net/aspose.words/document/compliance/
---
## Document.Compliance property

Ottiene la versione di conformità OOXML determinata dal contenuto del documento caricato. Ha senso solo per documenti OOXML.

```csharp
public OoxmlCompliance Compliance { get; }
```

### Osservazioni

Se hai creato un nuovo documento vuoto o carichi non OOXML document restituisce ilEcma376_2006 valore.

### Esempi

Mostra come leggere la versione di conformità Open Office XML di un documento caricato.

```csharp
// La versione di conformità varia tra i documenti creati da diverse versioni di Microsoft Word.
Document doc = new Document(MyDir + "Document.doc");

Assert.AreEqual(doc.Compliance, OoxmlCompliance.Ecma376_2006);

doc = new Document(MyDir + "Document.docx");

Assert.AreEqual(doc.Compliance, OoxmlCompliance.Iso29500_2008_Transitional);
```

### Guarda anche

* enum [OoxmlCompliance](../../../aspose.words.saving/ooxmlcompliance/)
* class [Document](../)
* spazio dei nomi [Aspose.Words](../../document/)
* assemblea [Aspose.Words](../../../)


