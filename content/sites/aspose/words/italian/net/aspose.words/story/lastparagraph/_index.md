---
title: Story.LastParagraph
second_title: Aspose.Words per .NET API Reference
description: Story proprietà. Ottiene lultimo paragrafo della storia.
type: docs
weight: 20
url: /it/net/aspose.words/story/lastparagraph/
---
## Story.LastParagraph property

Ottiene l'ultimo paragrafo della storia.

```csharp
public Paragraph LastParagraph { get; }
```

### Esempi

Mostra come spostare la posizione del cursore di un DocumentBuilder su un nodo specificato.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Run 1. ");

// Il generatore di documenti ha un cursore, che funge da parte del documento
// dove il builder aggiunge nuovi nodi quando utilizziamo i suoi metodi di costruzione del documento.
// Questo cursore funziona allo stesso modo del cursore lampeggiante di Microsoft Word,
// e finisce sempre subito dopo ogni nodo che il builder ha appena inserito.
// Per aggiungere contenuto a una parte diversa del documento,
// possiamo spostare il cursore su un nodo diverso con il metodo "MoveTo".
// Il cursore ora si trova davanti al nodo in cui lo abbiamo spostato.
// L'aggiunta di una seconda esecuzione la inserirà davanti alla prima.
builder.Writeln("Run 2. ");

Assert.AreEqual("Run 2. \rRun 1.", doc.GetText().Trim());

// Sposta il cursore alla fine del documento per continuare ad aggiungere il testo alla fine come prima.
builder.MoveTo(doc.LastSection.Body.LastParagraph);
builder.Writeln("Run 3. ");

Assert.AreEqual("Run 2. \rRun 1. \rRun 3.", doc.GetText().Trim());
```

### Guarda anche

* class [Paragraph](../../paragraph/)
* class [Story](../)
* spazio dei nomi [Aspose.Words](../../story/)
* assemblea [Aspose.Words](../../../)


