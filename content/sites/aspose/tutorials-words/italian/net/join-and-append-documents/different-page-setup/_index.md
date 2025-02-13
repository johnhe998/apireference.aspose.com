---
title: Impostazione pagina diversa
linktitle: Impostazione pagina diversa
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come aggiungere un documento con diverse impostazioni di configurazione della pagina utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/different-page-setup/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per aggiungere un documento con diverse impostazioni di configurazione della pagina a un altro documento. Il codice sorgente fornito mostra come configurare diverse impostazioni di pagina per i documenti di origine e di destinazione e garantire una continuazione e una numerazione corrette.

## Passaggio 1: impostare il progetto

Assicurati di avere i seguenti prerequisiti:

- Aspose.Words per la libreria .NET installata. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare il gestore di pacchetti NuGet per installarlo.
- Un percorso di directory del documento in cui si trovano i documenti di origine e di destinazione.

## Passaggio 2: apri i documenti di origine e di destinazione

 Apri i documenti di origine e di destinazione utilizzando il file`Document` costruttore di classe. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Passaggio 3: configurare le impostazioni della pagina per il documento di origine

Regola le impostazioni di configurazione della pagina del documento di origine per garantire una continuazione e una numerazione corrette. In questo esempio, impostiamo l'inizio della sezione su`SectionStart.Continuous` e riavviare la numerazione delle pagine. Ci assicuriamo inoltre che la larghezza, l'altezza e l'orientamento della pagina corrispondano all'ultima sezione del documento di destinazione.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## Passaggio 4: modificare la formattazione del paragrafo

 Per mantenere una formattazione corretta, scorrere tutti i paragrafi nel documento di origine e impostare l'estensione`KeepWithNext` proprietà a`true`. Ciò garantisce che i paragrafi rimangano uniti durante il processo di aggiunta.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Passaggio 5: aggiungere il documento di origine al documento di destinazione

 Usa il`AppendDocument` metodo del documento di destinazione per aggiungere il documento di origine modificato al documento di destinazione, preservando la formattazione di origine.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Passaggio 6: salvare il documento di destinazione

 Infine, salva il documento di destinazione modificato utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

Questo completa l'implementazione dell'aggiunta di un documento con diverse impostazioni di impostazione della pagina utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Different Page Setup utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//Impostare il documento di origine in modo che continui subito dopo la fine del documento di destinazione.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Riavvia la numerazione delle pagine all'inizio del documento di origine.
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	// Per garantire che ciò non accada quando il documento di origine ha impostazioni di configurazione della pagina diverse, assicurati che il file
	// le impostazioni sono identiche nell'ultima sezione del documento di destinazione.
	// Se ci sono ulteriori sezioni continue che seguono nel documento di origine,
	// questo dovrà essere ripetuto per quelle sezioni.
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	// Scorrere tutte le sezioni nel documento di origine.
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```