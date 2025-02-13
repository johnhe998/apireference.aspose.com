---
title: Enum ShowInBalloons
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Layout.ShowInBalloons enum. Specifica quali revisioni vengono visualizzate nei fumetti.
type: docs
weight: 3210
url: /it/net/aspose.words.layout/showinballoons/
---
## ShowInBalloons enumeration

Specifica quali revisioni vengono visualizzate nei fumetti.

```csharp
public enum ShowInBalloons
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| None | `0` | Rendering di inserire, eliminare e formattare le revisioni in linea. |
| Format | `1` | Render inserisce ed elimina le revisioni in linea, formatta le revisioni nei fumetti. |
| FormatAndDelete | `2` | Il rendering inserisce le revisioni in linea, elimina e formatta le revisioni nei fumetti. |

### Osservazioni

Si noti che le revisioni non vengono visualizzate in fumetti perShowInAnnotations .

### Esempi

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

* spazio dei nomi [Aspose.Words.Layout](../../aspose.words.layout/)
* assemblea [Aspose.Words](../../)


