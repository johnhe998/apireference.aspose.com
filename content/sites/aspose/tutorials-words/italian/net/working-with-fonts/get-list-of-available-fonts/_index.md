---
title: Ottieni l'elenco dei caratteri disponibili
linktitle: Ottieni l'elenco dei caratteri disponibili
second_title: Aspose.Words API di elaborazione dei documenti
description: In questo tutorial, scopri come ottenere l'elenco dei caratteri disponibili in Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fonts/get-list-of-available-fonts/
---
In questo tutorial, spiegheremo come ottenere l'elenco dei caratteri disponibili in Aspose.Words per .NET. L'elenco dei caratteri disponibili ti consente di sapere quali caratteri puoi utilizzare nei tuoi documenti. Ti guideremo passo dopo passo per aiutarti a comprendere e implementare il codice nel tuo progetto .NET.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti elementi:
- Conoscenza operativa del linguaggio di programmazione C#
- La libreria Aspose.Words per .NET installata nel tuo progetto

## Passaggio 1: definire la directory dei documenti
 Innanzitutto, devi impostare il percorso della directory nella posizione del documento di Word. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso appropriato.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: configura le origini dei caratteri
 Successivamente, creeremo un'istanza di`FontSettings` e ottieni le fonti di font esistenti usando il file`GetFontsSources()` metodo. Aggiungeremo anche una nuova fonte di font specificando una cartella contenente i font.

```csharp
// Configura le origini dei caratteri
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

// Aggiungi una nuova fonte di carattere
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## Passaggio 3: ottieni l'elenco dei caratteri disponibili
 Ora esploreremo i caratteri disponibili utilizzando il file`GetAvailableFonts()` metodo sulla prima fonte di carattere aggiornata.

```csharp
// Ottenere l'elenco dei caratteri disponibili
foreach(PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
Console.WriteLine("Font Family Name: " + fontInfo.FontFamilyName);
Console.WriteLine("Full font name: " + fontInfo.FullFontName);
Console.WriteLine("Version: " + fontInfo.Version);
Console.WriteLine("Path: " + fontInfo.FilePath);
}
```


### Esempio di codice sorgente per ottenere l'elenco dei caratteri disponibili utilizzando Aspose.Words per .NET 

```csharp

//Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Aggiungi una nuova cartella sorgente che istruirà Aspose.Words a cercare i caratteri nella seguente cartella.
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
// Aggiungi la cartella personalizzata che contiene i nostri font all'elenco delle fonti di font esistenti.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
	Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
	Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
	Console.WriteLine("Version  : " + fontInfo.Version);
	Console.WriteLine("FilePath : " + fontInfo.FilePath);
}

```

## Conclusione
In questo tutorial, abbiamo visto come ottenere l'elenco dei font disponibili in Aspose.Words per .NET. Questo ti consente di sapere quali caratteri puoi utilizzare nei tuoi documenti. Sentiti libero di utilizzare questa funzione per scegliere i caratteri appropriati per le tue esigenze.

### FAQ

#### D: Come posso recuperare l'elenco dei caratteri disponibili in Aspose.Words?

 R: Per recuperare l'elenco dei caratteri disponibili in Aspose.Words, puoi utilizzare il file`FontsProvider` classe e il`GetAvailableFonts` metodo. Questo metodo restituirà un elenco di tutti i font installati sul tuo sistema.

#### D: Posso filtrare l'elenco dei caratteri disponibili in base a determinati criteri in Aspose.Words?

R: Sì, puoi filtrare l'elenco dei caratteri disponibili in Aspose.Words utilizzando criteri specifici. Ad esempio, puoi filtrare i caratteri per famiglia, stile o lingua.

#### D: Come posso utilizzare l'elenco dei caratteri disponibili nei miei documenti Word?

 R: Per utilizzare l'elenco dei caratteri disponibili nei tuoi documenti Word, puoi sfogliare l'elenco e selezionare i caratteri appropriati utilizzando i metodi e le proprietà del`FontSettings` classe in Aspose.Words.