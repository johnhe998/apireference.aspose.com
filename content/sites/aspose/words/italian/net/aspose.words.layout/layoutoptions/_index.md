---
title: Class LayoutOptions
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Layout.LayoutOptions classe. Contiene le opzioni che consentono di controllare il processo di layout del documento.
type: docs
weight: 3150
url: /it/net/aspose.words.layout/layoutoptions/
---
## LayoutOptions class

Contiene le opzioni che consentono di controllare il processo di layout del documento.

```csharp
public class LayoutOptions
```

## Costruttori

| Nome | Descrizione |
| --- | --- |
| [LayoutOptions](layoutoptions/)() | Default_Costruttore |

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [Callback](../../aspose.words.layout/layoutoptions/callback/) { get; set; } | Ottiene o imposta[`IPageLayoutCallback`](../ipagelayoutcallback/)implementazione utilizzata dal modello di layout di pagina. |
| [CommentDisplayMode](../../aspose.words.layout/layoutoptions/commentdisplaymode/) { get; set; } | Ottiene o imposta il modo in cui vengono visualizzati i commenti. Il valore predefinito èShowInBalloons . |
| [ContinuousSectionPageNumberingRestart](../../aspose.words.layout/layoutoptions/continuoussectionpagenumberingrestart/) { get; set; } | Ottiene o imposta la modalità di comportamento per il calcolo dei numeri di pagina quando una sezione continua riavvia la numerazione delle pagine. |
| [IgnorePrinterMetrics](../../aspose.words.layout/layoutoptions/ignoreprintermetrics/) { get; set; } | Ottiene o imposta l'indicazione se l'opzione di compatibilità "Usa le metriche della stampante per il layout del documento" è ignorata. L'impostazione predefinita è True. |
| [RevisionOptions](../../aspose.words.layout/layoutoptions/revisionoptions/) { get; } | Ottiene le opzioni di revisione. |
| [ShowHiddenText](../../aspose.words.layout/layoutoptions/showhiddentext/) { get; set; } | Ottiene o imposta l'indicazione se il testo nascosto nel documento viene visualizzato. L'impostazione predefinita è False. |
| [ShowParagraphMarks](../../aspose.words.layout/layoutoptions/showparagraphmarks/) { get; set; } | Ottiene o imposta l'indicazione del rendering dei segni di paragrafo. L'impostazione predefinita è False. |
| [TextShaperFactory](../../aspose.words.layout/layoutoptions/textshaperfactory/) { get; set; } | Ottiene o imposta[`ITextShaperFactory`](../../aspose.words.shaping/itextshaperfactory/) implementazione utilizzata per le funzionalità di rendering di tipografia avanzata. |

### Osservazioni

Non crei direttamente istanze di questa classe. Utilizzare il[`LayoutOptions`](../../aspose.words/document/layoutoptions/)per accedere alle opzioni di layout per questo documento.

Nota che dopo aver modificato una qualsiasi delle opzioni presenti in questa classe,[`UpdatePageLayout`](../../aspose.words/document/updatepagelayout/) method dovrebbe essere chiamato per applicare le opzioni modificate al layout.

### Esempi

Mostra come nascondere il testo in un documento di output sottoposto a rendering.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
// Inserisci il testo nascosto, quindi specifica se desideriamo ometterlo da un documento renderizzato.
builder.Writeln("This text is not hidden.");
builder.Font.Hidden = true;
builder.Writeln("This text is hidden.");

doc.LayoutOptions.ShowHiddenText = showHiddenText;

doc.Save(ArtifactsDir + "Document.LayoutOptionsHiddenText.pdf");
```

Mostra come mostrare i segni di paragrafo in un documento di output sottoposto a rendering.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
// Aggiungi alcuni paragrafi, quindi attiva i segni di paragrafo per mostrare le estremità dei paragrafi
// con il simbolo di una crocetta (¶) quando eseguiamo il rendering del documento.
builder.Writeln("Hello world!");
builder.Writeln("Hello again!");

doc.LayoutOptions.ShowParagraphMarks = showParagraphMarks;

doc.Save(ArtifactsDir + "Document.LayoutOptionsParagraphMarks.pdf");
```

Mostra come modificare l'aspetto delle revisioni in un documento di output sottoposto a rendering.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserisci una revisione, quindi cambia il colore di tutte le revisioni in verde.
builder.Writeln("This is not a revision.");
doc.StartTrackRevisions("John Doe", DateTime.Now);
builder.Writeln("This is a revision.");
doc.StopTrackRevisions();
builder.Writeln("This is not a revision.");

// Rimuove la barra che appare a sinistra di ogni riga modificata.
doc.LayoutOptions.RevisionOptions.InsertedTextColor = RevisionColor.BrightGreen;
doc.LayoutOptions.RevisionOptions.ShowRevisionBars = false;

doc.Save(ArtifactsDir + "Document.LayoutOptionsRevisions.pdf");
```

### Guarda anche

* spazio dei nomi [Aspose.Words.Layout](../../aspose.words.layout/)
* assemblea [Aspose.Words](../../)


