---
title: Paragraph.JoinRunsWithSameFormatting
second_title: Aspose.Words per .NET API Reference
description: Paragraph metodo. Join viene eseguito con la stessa formattazione nel paragrafo.
type: docs
weight: 280
url: /it/net/aspose.words/paragraph/joinrunswithsameformatting/
---
## Paragraph.JoinRunsWithSameFormatting method

Join viene eseguito con la stessa formattazione nel paragrafo.

```csharp
public int JoinRunsWithSameFormatting()
```

### Valore di ritorno

Numero di join eseguiti. quando **N** le piste adiacenti vengono unite come contano **N - 1** si unisce.

### Esempi

Mostra come semplificare i paragrafi unendo esecuzioni superflue.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserisce quattro sequenze di testo nel paragrafo.
builder.Write("Run 1. ");
builder.Write("Run 2. ");
builder.Write("Run 3. ");
builder.Write("Run 4. ");

// Se apriamo questo documento in Microsoft Word, il paragrafo apparirà come un corpo di testo senza soluzione di continuità.
// Tuttavia, sarà composto da quattro esecuzioni separate con la stessa formattazione. Paragrafi frammentati come questo
// può verificarsi quando modifichiamo manualmente parti di un paragrafo più volte in Microsoft Word.
Paragraph para = builder.CurrentParagraph;

Assert.AreEqual(4, para.Runs.Count);

// Cambia lo stile dell'ultima corsa per distinguerla dalle prime tre.
para.Runs[3].Font.StyleIdentifier = StyleIdentifier.Emphasis;

// Possiamo eseguire il metodo "JoinRunsWithSameFormatting" per ottimizzare i contenuti del documento
// unendo corse simili in una, riducendone il conteggio complessivo.
// Questo metodo restituisce anche il numero di esecuzioni che questo metodo ha unito.
// Queste due unioni si sono verificate per combinare le esecuzioni #1, #2 e #3,
// tralasciando Run #4 perché ha uno stile incompatibile.
Assert.AreEqual(2, para.JoinRunsWithSameFormatting());

// Il numero di corse rimaste sarà uguale al conteggio originale
// meno il numero di unioni di esecuzione eseguite dal metodo "JoinRunsWithSameFormatting".
Assert.AreEqual(2, para.Runs.Count);
Assert.AreEqual("Run 1. Run 2. Run 3. ", para.Runs[0].Text);
Assert.AreEqual("Run 4. ", para.Runs[1].Text);
```

### Guarda anche

* class [Paragraph](../)
* spazio dei nomi [Aspose.Words](../../paragraph/)
* assemblea [Aspose.Words](../../../)


