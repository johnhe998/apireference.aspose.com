---
title: RevisionOptions.ShowInBalloons
second_title: Aspose.Words per .NET API Reference
description: RevisionOptions proprietà. Consente di specificare se le revisioni vengono visualizzate nei fumetti. Il valore predefinito èNone .
type: docs
weight: 160
url: /it/net/aspose.words.layout/revisionoptions/showinballoons/
---
## RevisionOptions.ShowInBalloons property

Consente di specificare se le revisioni vengono visualizzate nei fumetti. Il valore predefinito èNone .

```csharp
public ShowInBalloons ShowInBalloons { get; set; }
```

### Osservazioni

Si noti che le revisioni non vengono visualizzate in fumetti perShowInAnnotations .

### Esempi

Mostra come visualizzare le revisioni nei fumetti.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

// Per impostazione predefinita, il testo che è una revisione ha un colore diverso per differenziarlo dall'altro testo non di revisione.
// Imposta un'opzione di revisione per mostrare più dettagli su ogni revisione in un fumetto sul margine destro della pagina.
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.Save(ArtifactsDir + "Revision.ShowRevisionBalloons.pdf");
```

Mostra come modificare l'aspetto delle revisioni.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

// Ottieni l'oggetto RevisionOptions che controlla l'aspetto delle revisioni.
RevisionOptions revisionOptions = doc.LayoutOptions.RevisionOptions;

// Rendi le revisioni dell'inserimento in verde e corsivo.
revisionOptions.InsertedTextColor = RevisionColor.Green;
revisionOptions.InsertedTextEffect = RevisionTextEffect.Italic;

// Visualizza le revisioni dell'eliminazione in rosso e in grassetto.
revisionOptions.DeletedTextColor = RevisionColor.Red;
revisionOptions.DeletedTextEffect = RevisionTextEffect.Bold;

// Lo stesso testo apparirà due volte in una revisione del movimento:
// una volta al punto di partenza e una volta alla destinazione di arrivo.
// Rende giallo il testo della revisione da cui è stato spostato con un doppio barrato
// e doppia sottolineatura blu alla revisione spostata.
revisionOptions.MovedFromTextColor = RevisionColor.Yellow;
revisionOptions.MovedFromTextEffect = RevisionTextEffect.DoubleStrikeThrough;
revisionOptions.MovedToTextColor = RevisionColor.Blue;
revisionOptions.MovedFromTextEffect = RevisionTextEffect.DoubleUnderline;

// Rendering delle revisioni del formato in rosso scuro e grassetto.
revisionOptions.RevisedPropertiesColor = RevisionColor.DarkRed;
revisionOptions.RevisedPropertiesEffect = RevisionTextEffect.Bold;

// Posiziona una spessa barra blu scuro sul lato sinistro della pagina accanto alle righe interessate dalle revisioni.
revisionOptions.RevisionBarsColor = RevisionColor.DarkBlue;
revisionOptions.RevisionBarsWidth = 15.0f;

// Mostra segni di revisione e testo originale.
revisionOptions.ShowOriginalRevision = true;
revisionOptions.ShowRevisionMarks = true;

// Ottieni movimenti, eliminazioni, revisioni di formattazione e commenti da visualizzare in fumetti verdi
// sul lato destro della pagina.
revisionOptions.ShowInBalloons = ShowInBalloons.Format;
revisionOptions.CommentColor = RevisionColor.BrightGreen;

// Queste funzionalità sono applicabili solo a formati come .pdf o .jpg.
doc.Save(ArtifactsDir + "Revision.RevisionOptions.pdf");
```

### Guarda anche

* enum [ShowInBalloons](../../showinballoons/)
* class [RevisionOptions](../)
* spazio dei nomi [Aspose.Words.Layout](../../revisionoptions/)
* assemblea [Aspose.Words](../../../)


