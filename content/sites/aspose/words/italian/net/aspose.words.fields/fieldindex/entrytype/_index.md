---
title: FieldIndex.EntryType
second_title: Aspose.Words per .NET API Reference
description: FieldIndex proprietà. Ottiene o imposta un tipo di voce di indice utilizzato per creare lindice.
type: docs
weight: 40
url: /it/net/aspose.words.fields/fieldindex/entrytype/
---
## FieldIndex.EntryType property

Ottiene o imposta un tipo di voce di indice utilizzato per creare l'indice.

```csharp
public string EntryType { get; set; }
```

### Esempi

Mostra come creare un campo INDEX e quindi utilizzare i campi XE per popolarlo con le voci.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crea un campo INDEX che visualizzerà una voce per ogni campo XE trovato nel documento.
// Ogni voce visualizzerà il valore della proprietà Text del campo XE sul lato sinistro
// e la pagina contenente il campo XE a destra.
// Se i campi XE hanno lo stesso valore nella loro proprietà "Testo",
// il campo INDEX li raggrupperà in un'unica voce.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// Configura il campo INDEX solo per visualizzare i campi XE che rientrano nei limiti
// di un segnalibro denominato "MainBookmark" e le cui proprietà "EntryType" hanno valore "A".
// Per entrambi i campi INDEX e XE, la proprietà "EntryType" utilizza solo il primo carattere del relativo valore stringa.
index.BookmarkName = "MainBookmark";
index.EntryType = "A";

Assert.AreEqual(" INDEX  \\b MainBookmark \\f A", index.GetFieldCode());

// In una nuova pagina, avvia il segnalibro con un nome che corrisponda al valore
// della proprietà "NomeSegnalibro" del campo INDEX.
builder.InsertBreak(BreakType.PageBreak);
builder.StartBookmark("MainBookmark");

// Il campo INDEX raccoglierà questa voce perché è all'interno del segnalibro,
// e il suo tipo di voce corrisponde anche al tipo di voce del campo INDEX.
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Index entry 1";
indexEntry.EntryType = "A";

Assert.AreEqual(" XE  \"Index entry 1\" \\f A", indexEntry.GetFieldCode());

// Inserisci un campo XE che non comparirà nell'INDICE perché i tipi di voce non corrispondono.
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Index entry 2";
indexEntry.EntryType = "B";

// Termina il segnalibro e inserisci un campo XE in seguito.
// È dello stesso tipo del campo INDEX, ma non apparirà
// poiché è al di fuori dei limiti del segnalibro.
builder.EndBookmark("MainBookmark");
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Index entry 3";
indexEntry.EntryType = "A";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.Filtering.docx");
```

### Guarda anche

* class [FieldIndex](../)
* spazio dei nomi [Aspose.Words.Fields](../../fieldindex/)
* assemblea [Aspose.Words](../../../)


