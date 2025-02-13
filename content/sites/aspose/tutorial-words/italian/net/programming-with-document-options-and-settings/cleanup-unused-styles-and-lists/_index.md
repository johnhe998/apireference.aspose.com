---
title: Pulisci stili ed elenchi inutilizzati
linktitle: Pulisci stili ed elenchi inutilizzati
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida dettagliata per ripulire gli stili e gli elenchi inutilizzati in un documento con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

In questo tutorial, ti guideremo attraverso il codice sorgente C# per ripulire gli stili e gli elenchi inutilizzati con Aspose.Words per .NET. Questa funzione consente di rimuovere stili ed elenchi non utilizzati in un documento.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurarsi che nel progetto si faccia riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento

In questo passaggio, caricheremo il documento Word contenente gli stili e gli elenchi inutilizzati che vogliamo ripulire. Utilizzare il seguente codice per caricare il documento:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

## Passaggio 3: contare gli stili e gli elenchi prima della pulizia

Prima della pulizia, conteremo il numero di stili e liste presenti nel documento. Utilizzare il seguente codice per visualizzare i contatori:

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

Queste istruzioni mostrano il numero di stili e liste presenti nel documento prima della pulizia.

## Passaggio 4: ripulisci gli stili e gli elenchi inutilizzati

Ora puliamo gli stili e gli elenchi inutilizzati dal documento. Utilizzare il codice seguente per eseguire la pulizia:

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

 Questo codice elimina gli stili e gli elenchi inutilizzati dal documento utilizzando le opzioni specificate. In questo esempio, abbiamo abilitato il`UnusedStyles` opzione per rimuovere gli stili inutilizzati e disabilitare il`UnusedLists` opzione per mantenere gli elenchi anche se non vengono utilizzati.

## Passaggio 5: contare gli stili e gli elenchi dopo la pulizia

Dopo aver eseguito la pulizia, conteremo nuovamente gli stili e gli elenchi per verificare se sono stati compressi. Utilizzare il seguente codice per visualizzare i nuovi contatori:

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

Queste istruzioni mostrano il numero di stili e liste rimanenti dopo la pulizia.

### Codice sorgente di esempio per la pulizia di stili ed elenchi inutilizzati utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	// In combinazione con gli stili incorporati, il documento ora ha otto stili.
	// Uno stile personalizzato è contrassegnato come "usato" finché è presente del testo all'interno del documento
	// formattato in quello stile. Ciò significa che i 4 stili che abbiamo aggiunto sono attualmente inutilizzati.
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	//Pulisce gli stili e gli elenchi inutilizzati dal documento a seconda delle CleanupOptions specificate.
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

 Assicurarsi di specificare il percorso del documento corretto nel file`dataDir` variabile.

Ora hai imparato come ripulire gli stili e gli elenchi inutilizzati da un documento utilizzando Aspose.Words per .NET. Seguendo la guida dettagliata fornita in questo tutorial, puoi facilmente applicare questa funzione ai tuoi documenti.

