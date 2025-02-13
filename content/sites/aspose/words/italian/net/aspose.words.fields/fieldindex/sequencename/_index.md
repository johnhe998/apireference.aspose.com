---
title: FieldIndex.SequenceName
second_title: Aspose.Words per .NET API Reference
description: FieldIndex proprietà. Ottiene o imposta il nome di una sequenza il cui numero è incluso nel numero di pagina.
type: docs
weight: 150
url: /it/net/aspose.words.fields/fieldindex/sequencename/
---
## FieldIndex.SequenceName property

Ottiene o imposta il nome di una sequenza il cui numero è incluso nel numero di pagina.

```csharp
public string SequenceName { get; set; }
```

### Esempi

Mostra come dividere un documento in porzioni combinando i campi INDEX e SEQ.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crea un campo INDEX che visualizzerà una voce per ogni campo XE trovato nel documento.
// Ogni voce visualizzerà il valore della proprietà Text del campo XE sul lato sinistro,
// e il numero della pagina che contiene il campo XE a destra.
// Se i campi XE hanno lo stesso valore nella loro proprietà "Testo",
// il campo INDEX li raggrupperà in un'unica voce.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// Nella proprietà SequenceName, denominare una sequenza di campi SEQ. Verrà ora visualizzata anche ogni voce di questo campo INDEX
// il numero su cui si trova il conteggio della sequenza nella posizione del campo XE che ha creato questa voce.
index.SequenceName = "MySequence";

// Imposta il testo intorno alla sequenza e ai numeri di pagina per spiegare il loro significato all'utente.
// Una voce creata con questa configurazione visualizzerà qualcosa come "MySequence at 1 on page 1" al suo numero di pagina.
// PageNumberSeparator e SequenceSeparator non possono essere più lunghi di 15 caratteri.
index.PageNumberSeparator = "\tMySequence at ";
index.SequenceSeparator = " on page ";
Assert.IsTrue(index.HasSequenceName);

Assert.AreEqual(" INDEX  \\s MySequence \\e \"\tMySequence at \" \\d \" on page \"", index.GetFieldCode());

// I campi SEQ mostrano un conteggio che aumenta ad ogni campo SEQ.
// Questi campi mantengono anche conteggi separati per ciascuna sequenza denominata univoca
// identificato dalla proprietà "SequenceIdentifier" del campo SEQ.
// Inserisce un campo SEQ che sposta la sequenza "MySequence" a 1.
// Questo campo non è diverso dal normale testo del documento. Non apparirà sul sommario di un campo INDEX.
builder.InsertBreak(BreakType.PageBreak);
FieldSeq sequenceField = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
sequenceField.SequenceIdentifier = "MySequence";

Assert.AreEqual(" SEQ  MySequence", sequenceField.GetFieldCode());

// Inserisci un campo XE che creerà una voce nel campo INDEX.
// Poiché "MySequence" è a 1 e questo campo XE è a pagina 2, insieme ai separatori personalizzati che abbiamo definito sopra,
// la voce INDEX di questo campo visualizzerà "Cat" sul lato sinistro e "MySequence at 1 on page 2" sulla destra.
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Cat";

Assert.AreEqual(" XE  Cat", indexEntry.GetFieldCode());

// Inserisci un'interruzione di pagina e usa i campi SEQ per far avanzare "MySequence" a 3.
builder.InsertBreak(BreakType.PageBreak);
sequenceField = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
sequenceField.SequenceIdentifier = "MySequence";
sequenceField = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
sequenceField.SequenceIdentifier = "MySequence";

// Inserisce un campo XE con la stessa proprietà Text di quello sopra.
// La voce INDEX raggrupperà i campi XE con valori corrispondenti nella proprietà "Testo".
// in una voce invece di inserire una voce per ogni campo XE.
// Poiché siamo a pagina 2 con "MySequence" a 3, ", 3 a pagina 3" verranno aggiunti alla stessa voce INDEX di cui sopra.
// La parte del numero di pagina di quella voce INDEX ora visualizzerà "MySequence at 1 on page 2, 3 on page 3".
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Cat";

// Inserisce un campo XE con un valore della proprietà Text nuovo e univoco.
// Questo aggiungerà una nuova voce, con MySequence in 3 a pagina 4.
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Dog";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.Sequence.docx");
```

### Guarda anche

* class [FieldIndex](../)
* spazio dei nomi [Aspose.Words.Fields](../../fieldindex/)
* assemblea [Aspose.Words](../../../)


