---
title: ParagraphFormat.SpaceBeforeAuto
second_title: Aspose.Words per .NET API Reference
description: ParagraphFormat proprietà. Vero se la quantità di spaziatura prima del paragrafo viene impostata automaticamente.
type: docs
weight: 320
url: /it/net/aspose.words/paragraphformat/spacebeforeauto/
---
## ParagraphFormat.SpaceBeforeAuto property

Vero se la quantità di spaziatura prima del paragrafo viene impostata automaticamente.

```csharp
public bool SpaceBeforeAuto { get; set; }
```

### Osservazioni

Se impostato su true, sovrascrive l'effetto di[`SpaceBefore`](../spacebefore/).

Quando si imposta il paragrafo Spazio prima e Spazio dopo su Auto, Microsoft Word aggiunge automaticamente 14 punti di spaziatura tra i paragrafi in base alle seguenti regole:

* Normalmente, la spaziatura viene aggiunta dopo tutti i paragrafi.
* In un elenco puntato o numerato, la spaziatura viene aggiunta solo dopo l'ultimo elemento nell'elenco. La spaziatura non viene aggiunta tra gli elementi dell'elenco.
* In un elenco puntato o numerato nidificato non viene aggiunta la spaziatura.
* La spaziatura viene normalmente aggiunta dopo una tabella.
* La spaziatura non viene aggiunta dopo una tabella se è l'ultimo blocco in una cella di tabella.
* La spaziatura non viene aggiunta dopo l'ultimo paragrafo in una cella di tabella.

### Esempi

Mostra come impostare la spaziatura automatica dei paragrafi.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Applica una grande quantità di spaziatura prima e dopo i paragrafi che questo builder creerà.
builder.ParagraphFormat.SpaceBefore = 24;
builder.ParagraphFormat.SpaceAfter = 24;

// Imposta questi flag su "true" per applicare la spaziatura automatica,
// ignorando efficacemente la spaziatura nelle proprietà che abbiamo impostato sopra.
// Lasciali come "falsi" applicherà la nostra spaziatura dei paragrafi personalizzata.
builder.ParagraphFormat.SpaceAfterAuto = autoSpacing;
builder.ParagraphFormat.SpaceBeforeAuto = autoSpacing;

// Inserisci due paragrafi che avranno spazi sopra e sotto e salva il documento.
builder.Writeln("Paragraph 1.");
builder.Writeln("Paragraph 2.");

doc.Save(ArtifactsDir + "ParagraphFormat.ParagraphSpacingAuto.docx");
```

### Guarda anche

* class [ParagraphFormat](../)
* spazio dei nomi [Aspose.Words](../../paragraphformat/)
* assemblea [Aspose.Words](../../../)


