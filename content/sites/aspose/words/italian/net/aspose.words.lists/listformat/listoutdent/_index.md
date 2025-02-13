---
title: ListFormat.ListOutdent
second_title: Aspose.Words per .NET API Reference
description: ListFormat metodo. Diminuisce di un livello il livello dellelenco del paragrafo corrente.
type: docs
weight: 80
url: /it/net/aspose.words.lists/listformat/listoutdent/
---
## ListFormat.ListOutdent method

Diminuisce di un livello il livello dell'elenco del paragrafo corrente.

```csharp
public void ListOutdent()
```

### Osservazioni

Questo metodo modifica il livello dell'elenco e applica le proprietà di formattazione del nuovo livello.

Nei documenti Word, gli elenchi possono essere formati da un massimo di nove livelli. List formatting per ogni livello specifica quale punto elenco o numero viene utilizzato, rientro sinistro, spazio tra punto elenco e testo, ecc.

### Esempi

Mostra come creare elenchi puntati e numerati.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Aspose.Words main advantages are:");

// Un elenco ci consente di organizzare e decorare insiemi di paragrafi con simboli e rientri prefissi.
// Possiamo creare liste nidificate aumentando il livello di rientro. 
// Possiamo iniziare e terminare un elenco utilizzando la proprietà "ListFormat" di un generatore di documenti. 
// Ogni paragrafo che aggiungiamo tra l'inizio e la fine di un elenco diventerà un elemento nell'elenco.
// Di seguito sono riportati due tipi di elenchi che possiamo creare con un generatore di documenti.
// 1 - Un elenco puntato:
// Questo elenco applicherà un trattino e un simbolo di punto elenco ("•") prima di ogni paragrafo.
builder.ListFormat.ApplyBulletDefault();
builder.Writeln("Great performance");
builder.Writeln("High reliability");
builder.Writeln("Quality code and working");
builder.Writeln("Wide variety of features");
builder.Writeln("Easy to understand API");

// Termina l'elenco puntato.
builder.ListFormat.RemoveNumbers();

builder.InsertBreak(BreakType.ParagraphBreak);
builder.Writeln("Aspose.Words allows:");

// 2 - Un elenco numerato:
// Gli elenchi numerati creano un ordine logico per i loro paragrafi numerando ogni elemento.
builder.ListFormat.ApplyNumberDefault();

// Questo paragrafo è il primo elemento. Il primo elemento di un elenco numerato avrà un "1". come simbolo della voce di elenco.
builder.Writeln("Opening documents from different formats:");

Assert.AreEqual(0, builder.ListFormat.ListLevelNumber);

// Chiama il metodo "ListIndent" per aumentare il livello di elenco corrente,
// che avvierà un nuovo elenco autonomo, con un rientro più profondo, all'elemento corrente del primo livello di elenco.
builder.ListFormat.ListIndent();

Assert.AreEqual(1, builder.ListFormat.ListLevelNumber);

// Questi sono i primi tre elementi dell'elenco del secondo livello di elenco, che manterranno un conteggio
// indipendente dal conteggio del primo livello di lista. Secondo l'attuale formato dell'elenco,
// avranno i simboli di "a.", "b." e "c.".
builder.Writeln("DOC");
builder.Writeln("PDF");
builder.Writeln("HTML");

// Chiama il metodo "ListOutdent" per tornare al livello di elenco precedente.
builder.ListFormat.ListOutdent();

Assert.AreEqual(0, builder.ListFormat.ListLevelNumber);

// Questi due paragrafi continueranno il conteggio del primo livello di elenco.
// Questi elementi avranno i simboli "2." e "3".
builder.Writeln("Processing documents");
builder.Writeln("Saving documents in different formats:");

// Se aumentiamo il livello dell'elenco a un livello a cui abbiamo aggiunto elementi in precedenza,
// la lista annidata sarà separata dalla precedente e la sua numerazione partirà dall'inizio. 
// Questi elementi dell'elenco avranno i simboli di "a.", "b.", "c.", "d." ed "e".
builder.ListFormat.ListIndent();
builder.Writeln("DOC");
builder.Writeln("PDF");
builder.Writeln("HTML");
builder.Writeln("MHTML");
builder.Writeln("Plain text");

// Annulla nuovamente il livello dell'elenco.
builder.ListFormat.ListOutdent();
builder.Writeln("Doing many other things!");

// Termina l'elenco numerato.
builder.ListFormat.RemoveNumbers();

doc.Save(ArtifactsDir + "Lists.ApplyDefaultBulletsAndNumbers.docx");
```

### Guarda anche

* class [ListFormat](../)
* spazio dei nomi [Aspose.Words.Lists](../../listformat/)
* assemblea [Aspose.Words](../../../)


