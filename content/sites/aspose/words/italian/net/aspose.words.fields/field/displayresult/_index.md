---
title: Field.DisplayResult
second_title: Aspose.Words per .NET API Reference
description: Field proprietà. Ottiene il testo che rappresenta il risultato del campo visualizzato.
type: docs
weight: 10
url: /it/net/aspose.words.fields/field/displayresult/
---
## Field.DisplayResult property

Ottiene il testo che rappresenta il risultato del campo visualizzato.

```csharp
public string DisplayResult { get; }
```

### Osservazioni

Il[`UpdateListLabels`](../../../aspose.words/document/updatelistlabels/) è necessario chiamare il metodo per ottenere il valore corretto per il [`FieldListNum`](../../fieldlistnum/) ,[`FieldAutoNum`](../../fieldautonum/) ,[`FieldAutoNumOut`](../../fieldautonumout/) e[`FieldAutoNumLgl`](../../fieldautonumlgl/) campi.

### Esempi

Mostra come ottenere il testo reale visualizzato in un campo nel documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("This document was written by ");
FieldAuthor fieldAuthor = (FieldAuthor)builder.InsertField(FieldType.FieldAuthor, true);
fieldAuthor.AuthorName = "John Doe";

// Possiamo usare la proprietà DisplayResult per verificare quale testo esatto
// un campo verrebbe visualizzato al suo posto nel documento.
Assert.AreEqual(string.Empty, fieldAuthor.DisplayResult);

 // I campi non mantengono valori di risultato accurati in tempo reale.
// Per assicurarti che i nostri campi visualizzino risultati accurati in qualsiasi momento,
// come prima di un'operazione di salvataggio, è necessario aggiornarli manualmente.
fieldAuthor.Update();

Assert.AreEqual("John Doe", fieldAuthor.DisplayResult);

doc.Save(ArtifactsDir + "Field.DisplayResult.docx");
```

### Guarda anche

* class [Field](../)
* spazio dei nomi [Aspose.Words.Fields](../../field/)
* assemblea [Aspose.Words](../../../)


