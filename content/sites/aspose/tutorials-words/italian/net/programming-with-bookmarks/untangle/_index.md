---
title: Districare nel documento di Word
linktitle: Districare nel documento di Word
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come districare i segnalibri nidificati nei documenti word nelle righe adiacenti della tabella utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-bookmarks/untangle/
---

In questo articolo, esploreremo il codice sorgente C# sopra per capire come usare la funzione Untangle nella libreria Aspose.Words per .NET. Questa funzione svela i segnalibri nidificati che si trovano nelle righe adiacenti della tabella.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: sfoglia i segnalibri del documento

Usiamo un ciclo foreach per scorrere tutti i segnalibri presenti nel documento:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     // Codice per la gestione dei segnalibri qui
}
```

## Passaggio 2: ottieni le righe principali dai segnalibri

 Noi usiamo il`GetAncestor`metodi per recuperare le righe padre dei nodi iniziale e finale del segnalibro:

```csharp
Row row1 = (Row)bookmark.BookmarkStart.GetAncestor(typeof(Row));
Row row2 = (Row)bookmark.BookmarkEnd.GetAncestor(typeof(Row));
```

## Passaggio 3: districare i segnalibri nidificati

Se vengono trovate entrambe le righe principali e il segnalibro inizia e finisce in righe adiacenti, spostiamo il nodo finale del segnalibro alla fine dell'ultimo paragrafo dell'ultima cella nella riga superiore:

```csharp
if (row1 != null && row2 != null && row1.NextSibling == row2)
     row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
```

### Esempio di codice sorgente per Untangle utilizzando Aspose.Words per .NET

Ecco l'esempio di codice sorgente completo per districare i segnalibri nidificati utilizzando Aspose.Words per .NET:

```csharp

	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		// Ottieni la riga padre sia del segnalibro che del nodo finale del segnalibro.
		Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
		Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

		// Se entrambe le righe vengono trovate correttamente e l'inizio e la fine del segnalibro sono contenuti in righe adiacenti,
		// sposta il nodo finale del segnalibro alla fine dell'ultimo paragrafo nell'ultima cella della riga superiore.
		if (row1 != null && row2 != null && row1.NextSibling == row2)
			row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
	}

```

## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come usare la funzione Untangle di Aspose.Words per .NET. Abbiamo seguito una guida dettagliata per districare i segnalibri nidificati nelle righe adiacenti della tabella.

### FAQ

#### D: La funzione Untangle funziona solo con i segnalibri nidificati nelle righe adiacenti della tabella?

R: Sì, la funzione Untangle è progettata specificamente per districare i segnalibri nidificati che si trovano nelle righe adiacenti della tabella. Se i segnalibri non sono in righe adiacenti, questa funzione non sarà applicabile.

#### D: Come posso identificare i segnalibri nidificati nel mio documento di Word?

R: È possibile identificare i segnalibri nidificati scorrendo i segnalibri nel documento e verificando se il segnalibro iniziale e il segnalibro finale si trovano nelle righe adiacenti della tabella. È possibile utilizzare il codice sorgente fornito in questo articolo come punto di partenza per implementare questa funzionalità.

#### D: La funzione Unscramble modifica il contenuto del documento originale?

R: Sì, la funzione Untangle modifica il documento originale spostando il nodo finale del segnalibro alla fine dell'ultimo paragrafo dell'ultima cella nella riga superiore. Assicurati di salvare una copia di backup del documento prima di applicare questa funzione.

#### D: Come posso districare i segnalibri nidificati in altri tipi di elementi del documento, come sezioni o paragrafi?

R: La funzione Untangle presentata in questo articolo è specificamente progettata per districare i segnalibri nidificati nelle righe adiacenti della tabella. Se si desidera districare i segnalibri nidificati in altri elementi del documento, sarà necessario adattare il codice di conseguenza e utilizzare metodi appropriati per accedere agli elementi desiderati.

#### D: Esistono altri metodi per districare i segnalibri nidificati in un documento di Word utilizzando Aspose.Words per .NET?

R: Il metodo presentato in questo articolo è un metodo comune per districare i segnalibri nidificati nelle righe adiacenti della tabella. Tuttavia, potrebbero esserci altri approcci o tecniche a seconda delle esigenze specifiche del progetto. Puoi consultare la documentazione ufficiale di Aspose.Words per esplorare ulteriormente le funzionalità disponibili.