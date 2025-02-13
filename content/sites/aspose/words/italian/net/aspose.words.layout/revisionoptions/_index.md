---
title: Class RevisionOptions
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Layout.RevisionOptions classe. Consente di controllare come vengono gestite le revisioni del documento durante il processo di impaginazione.
type: docs
weight: 3190
url: /it/net/aspose.words.layout/revisionoptions/
---
## RevisionOptions class

Consente di controllare come vengono gestite le revisioni del documento durante il processo di impaginazione.

```csharp
public class RevisionOptions
```

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [CommentColor](../../aspose.words.layout/revisionoptions/commentcolor/) { get; set; } | Consente di specificare il colore da utilizzare per i commenti. Il valore predefinito èRed . |
| [DeletedTextColor](../../aspose.words.layout/revisionoptions/deletedtextcolor/) { get; set; } | Consente di specificare il colore da utilizzare per il contenuto eliminatoDeletion . Il valore predefinito èByAuthor . |
| [DeletedTextEffect](../../aspose.words.layout/revisionoptions/deletedtexteffect/) { get; set; } | Consente di specificare l'effetto da applicare al contenuto eliminatoDeletion . Il valore predefinito èStrikeThrough |
| [InsertedTextColor](../../aspose.words.layout/revisionoptions/insertedtextcolor/) { get; set; } | Consente di specificare il colore da utilizzare per il contenuto inseritoInsertion . Il valore predefinito èByAuthor . |
| [InsertedTextEffect](../../aspose.words.layout/revisionoptions/insertedtexteffect/) { get; set; } | Consente di specificare l'effetto da applicare al contenuto inseritoInsertion . Il valore predefinito èUnderline . |
| [MeasurementUnit](../../aspose.words.layout/revisionoptions/measurementunit/) { get; set; } | Consente di specificare le unità di misura per i commenti di revisione. Il valore predefinito èCentimeters |
| [MovedFromTextColor](../../aspose.words.layout/revisionoptions/movedfromtextcolor/) { get; set; } | Consente di specificare il colore da utilizzare per le aree da cui è stato spostato il contenutoMoving . Il valore predefinito èByAuthor . |
| [MovedFromTextEffect](../../aspose.words.layout/revisionoptions/movedfromtexteffect/) { get; set; } | Consente di specificare l'effetto da applicare alle aree da cui è stato spostato il contenutoMoving . Il valore predefinito èDoubleStrikeThrough |
| [MovedToTextColor](../../aspose.words.layout/revisionoptions/movedtotextcolor/) { get; set; } | Consente di specificare il colore da utilizzare per le aree in cui è stato spostato il contenutoMoving . Il valore predefinito èByAuthor . |
| [MovedToTextEffect](../../aspose.words.layout/revisionoptions/movedtotexteffect/) { get; set; } | Consente di specificare l'effetto da applicare alle aree in cui è stato spostato il contenutoMoving . Il valore predefinito èDoubleUnderline |
| [RevisedPropertiesColor](../../aspose.words.layout/revisionoptions/revisedpropertiescolor/) { get; set; } | Consente di specificare il colore da utilizzare per il contenuto con modifiche alle proprietà di formattazioneFormatChange Il valore predefinito èNoHighlight . |
| [RevisedPropertiesEffect](../../aspose.words.layout/revisionoptions/revisedpropertieseffect/) { get; set; } | Consente di specificare l'effetto per le aree di contenuto con modifiche alle proprietà di formattazioneFormatChange Il valore predefinito èNone |
| [RevisionBarsColor](../../aspose.words.layout/revisionoptions/revisionbarscolor/) { get; set; } | Consente di specificare il colore da utilizzare per le barre laterali che identificano le righe del documento contenenti informazioni riviste. Il valore predefinito èRed . |
| [RevisionBarsPosition](../../aspose.words.layout/revisionoptions/revisionbarsposition/) { get; set; } | Ottiene o imposta la posizione di rendering delle barre di revisione. Il valore predefinito èOutside . |
| [RevisionBarsWidth](../../aspose.words.layout/revisionoptions/revisionbarswidth/) { get; set; } | Ottiene o imposta la larghezza delle barre di revisione, i punti. |
| [ShowInBalloons](../../aspose.words.layout/revisionoptions/showinballoons/) { get; set; } | Consente di specificare se le revisioni vengono visualizzate nei fumetti. Il valore predefinito èNone . |
| [ShowOriginalRevision](../../aspose.words.layout/revisionoptions/showoriginalrevision/) { get; set; } | Consente di specificare se visualizzare il testo originale anziché quello rivisto. Il valore predefinito è False. |
| [ShowRevisionBars](../../aspose.words.layout/revisionoptions/showrevisionbars/) { get; set; } | Consente di specificare se le barre di revisione devono essere visualizzate vicino a righe contenenti contenuto rivisto. Il valore predefinito è True. |
| [ShowRevisionMarks](../../aspose.words.layout/revisionoptions/showrevisionmarks/) { get; set; } | Consente di specificare se il testo di revisione deve essere contrassegnato con un markup di formattazione speciale. Il valore predefinito è True. |

### Esempi

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


