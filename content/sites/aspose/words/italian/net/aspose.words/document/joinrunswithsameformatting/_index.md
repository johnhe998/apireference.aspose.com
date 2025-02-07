---
title: Document.JoinRunsWithSameFormatting
second_title: Aspose.Words per .NET API Reference
description: Document metodo. Joins viene eseguito con la stessa formattazione in tutti i paragrafi del documento.
type: docs
weight: 600
url: /it/net/aspose.words/document/joinrunswithsameformatting/
---
## Document.JoinRunsWithSameFormatting method

Joins viene eseguito con la stessa formattazione in tutti i paragrafi del documento.

```csharp
public int JoinRunsWithSameFormatting()
```

### Valore di ritorno

Numero di join eseguiti. quando **N** le piste adiacenti vengono unite come contano **N - 1** si unisce.

### Osservazioni

Questo è un metodo di ottimizzazione. Alcuni documenti contengono esecuzioni adiacenti con la stessa formattazione. Di solito ciò si verifica se un documento è stato modificato manualmente in modo intensivo. È possibile ridurre le dimensioni del documento e accelerare l'ulteriore elaborazione unendo queste esecuzioni.

L'operazione controlla ogni[`Paragraph`](../../paragraph/) nodo nel documento per adiacente[`Run`](../../run/) nodi con proprietà identiche. Ignora gli identificatori univoci utilizzati per tenere traccia delle sessioni di modifica della creazione e modifica di run . La prima esecuzione in ogni sequenza di unione accumula tutto il testo. Le corse rimanenti vengono eliminate dal documento.

### Esempi

Mostra come unire le esecuzioni in un documento per ridurre le esecuzioni non necessarie.

```csharp
// Apre un documento che contiene sequenze di testo adiacenti con formattazione identica,
// che si verifica comunemente se modifichiamo lo stesso paragrafo più volte in Microsoft Word.
Document doc = new Document(MyDir + "Rendering.docx");

// Se un numero qualsiasi di queste esecuzioni è adiacente con formattazione identica,
// il documento potrebbe essere semplificato.
Assert.AreEqual(317, doc.GetChildNodes(NodeType.Run, true).Count);

// Combina tali esecuzioni con questo metodo e verifica il numero di join di esecuzione che avranno luogo.
Assert.AreEqual(121, doc.JoinRunsWithSameFormatting());

// Il numero di join e il numero di esecuzioni che abbiamo dopo il join
// dovrebbe sommare il numero di esecuzioni che avevamo inizialmente.
Assert.AreEqual(196, doc.GetChildNodes(NodeType.Run, true).Count);
```

### Guarda anche

* class [Document](../)
* spazio dei nomi [Aspose.Words](../../document/)
* assemblea [Aspose.Words](../../../)


