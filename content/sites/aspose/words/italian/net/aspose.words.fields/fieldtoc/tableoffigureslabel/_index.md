---
title: FieldToc.TableOfFiguresLabel
second_title: Aspose.Words per .NET API Reference
description: FieldToc proprietà. Ottiene o imposta il nome dellidentificatore di sequenza utilizzato durante la creazione di una tabella di cifre.
type: docs
weight: 160
url: /it/net/aspose.words.fields/fieldtoc/tableoffigureslabel/
---
## FieldToc.TableOfFiguresLabel property

Ottiene o imposta il nome dell'identificatore di sequenza utilizzato durante la creazione di una tabella di cifre.

```csharp
public string TableOfFiguresLabel { get; set; }
```

### Esempi

Mostra come popolare un campo TOC con voci utilizzando i campi SEQ.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Un campo TOC può creare una voce nel suo sommario per ogni campo SEQ trovato nel documento.
// Ogni voce contiene il paragrafo che include il campo SEQ e il numero della pagina su cui appare il campo.
FieldToc fieldToc = (FieldToc)builder.InsertField(FieldType.FieldTOC, true);

// I campi SEQ mostrano un conteggio che aumenta ad ogni campo SEQ.
// Questi campi mantengono anche conteggi separati per ciascuna sequenza denominata univoca
// identificato dalla proprietà "SequenceIdentifier" del campo SEQ.
// Utilizzare la proprietà "TableOfFiguresLabel" per denominare una sequenza principale per il sommario.
// Ora, questo sommario creerà solo voci dai campi SEQ con il loro "SequenceIdentifier" impostato su "MySequence".
fieldToc.TableOfFiguresLabel = "MySequence";

// Possiamo nominare un'altra sequenza di campi SEQ nella proprietà "PrefixedSequenceIdentifier".
 // I campi SEQ di questa sequenza di prefissi non creeranno voci TOC.
// Ogni voce TOC creata da un campo SEQ della sequenza principale ora visualizzerà anche il conteggio
// la sequenza del prefisso è attualmente attiva nel campo SEQ della sequenza primaria che ha effettuato la voce.
fieldToc.PrefixedSequenceIdentifier = "PrefixSequence";

// Ogni voce TOC visualizzerà il conteggio della sequenza del prefisso immediatamente a sinistra
// del numero di pagina su cui appare il campo SEQ della sequenza principale.
// Possiamo specificare un separatore personalizzato che apparirà tra questi due numeri.
fieldToc.SequenceSeparator = ">";

Assert.AreEqual(" TOC  \\c MySequence \\s PrefixSequence \\d >", fieldToc.GetFieldCode());

builder.InsertBreak(BreakType.PageBreak);

// Esistono due modi per utilizzare i campi SEQ per popolare questo sommario.
// 1 - Inserimento di un campo SEQ che appartiene alla sequenza di prefissi del TOC:
// Questo campo incrementerà il conteggio della sequenza SEQ per "PrefixSequence" di 1.
// Poiché questo campo non appartiene alla sequenza principale identificata
// dalla proprietà "TableOfFiguresLabel" del sommario, non apparirà come voce.
FieldSeq fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "PrefixSequence";
builder.InsertParagraph();

Assert.AreEqual(" SEQ  PrefixSequence", fieldSeq.GetFieldCode());

// 2 - Inserimento di un campo SEQ che appartiene alla sequenza principale del TOC:
// Questo campo SEQ creerà una voce nel sommario.
// La voce TOC conterrà il paragrafo in cui si trova il campo SEQ e il numero della pagina in cui appare.
// Questa voce visualizzerà anche il conteggio a cui si trova attualmente la sequenza di prefissi,
// separato dal numero di pagina dal valore nella proprietà SeqenceSeparator del sommario.
// Il conteggio "PrefixSequence" è a 1, questo campo SEQ della sequenza principale è a pagina 2,
// e il separatore è ">", quindi la voce visualizzerà "1>2".
builder.Write("First TOC entry, MySequence #");
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "MySequence";

Assert.AreEqual(" SEQ  MySequence", fieldSeq.GetFieldCode());

// Inserisci una pagina, fai avanzare la sequenza del prefisso di 2 e inserisci un campo SEQ per creare una voce TOC in seguito.
// La sequenza del prefisso è ora a 2 e il campo SEQ della sequenza principale è a pagina 3,
// quindi la voce TOC visualizzerà "2>3" al conteggio delle pagine.
builder.InsertBreak(BreakType.PageBreak);
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "PrefixSequence";
builder.InsertParagraph();
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
builder.Write("Second TOC entry, MySequence #");
fieldSeq.SequenceIdentifier = "MySequence";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.TOC.SEQ.docx");
```

### Guarda anche

* class [FieldToc](../)
* spazio dei nomi [Aspose.Words.Fields](../../fieldtoc/)
* assemblea [Aspose.Words](../../../)


