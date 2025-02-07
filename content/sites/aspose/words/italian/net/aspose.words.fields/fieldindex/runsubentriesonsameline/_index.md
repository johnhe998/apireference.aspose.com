---
title: FieldIndex.RunSubentriesOnSameLine
second_title: Aspose.Words per .NET API Reference
description: FieldIndex proprietà. Ottiene o imposta se eseguire voci secondarie nella stessa riga della voce principale.
type: docs
weight: 140
url: /it/net/aspose.words.fields/fieldindex/runsubentriesonsameline/
---
## FieldIndex.RunSubentriesOnSameLine property

Ottiene o imposta se eseguire voci secondarie nella stessa riga della voce principale.

```csharp
public bool RunSubentriesOnSameLine { get; set; }
```

### Esempi

Mostra come lavorare con le sottovoci in un campo INDEX.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crea un campo INDEX che visualizzerà una voce per ogni campo XE trovato nel documento.
// Ogni voce visualizzerà il valore della proprietà Text del campo XE sul lato sinistro,
// e il numero della pagina che contiene il campo XE a destra.
// La voce INDEX raccoglierà tutti i campi XE con valori corrispondenti nella proprietà "Text".
// in una voce invece di inserire una voce per ogni campo XE.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);
index.PageNumberSeparator = ", see page ";
index.Heading = "A";

// Campi XE che hanno una proprietà Text il cui valore diventa l'intestazione della voce INDEX.
// Se questo valore contiene due segmenti di stringa divisi da due punti (la voce INDEX tratterà :) delimitatore,
// il primo segmento è l'intestazione e il secondo segmento diventerà il sottotitolo.
// Il campo INDEX prima raggruppa le voci in ordine alfabetico, quindi, se sono presenti più campi XE con lo stesso
// intestazioni, il campo INDEX le sottogruppi ulteriormente in base ai valori di queste intestazioni.
// Possono esserci più livelli di sottoraggruppamento, a seconda di quante volte
// le proprietà del testo dei campi XE vengono segmentate in questo modo.
 // Per impostazione predefinita, un gruppo di voci del campo INDEX creerà una nuova riga per ogni sottotitolo all'interno di questo gruppo.
// Possiamo impostare il flag RunSubentriesOnSameLine su true per mantenere l'intestazione,
// e ogni sottotitolo del gruppo invece su una riga, il che renderà il campo INDEX più compatto.
index.RunSubentriesOnSameLine = runSubentriesOnTheSameLine;

if (runSubentriesOnTheSameLine)
    Assert.AreEqual(" INDEX  \\e \", see page \" \\h A \\r", index.GetFieldCode());
else
    Assert.AreEqual(" INDEX  \\e \", see page \" \\h A", index.GetFieldCode());

// Inserisce due campi XE, ciascuno su una nuova pagina, e con la stessa intestazione denominata "Intestazione 1",
// che il campo INDEX utilizzerà per raggrupparli.
// Se RunSubentriesOnSameLine è false, la tabella INDEX creerà tre righe:
// una riga per l'intestazione di raggruppamento "Titolo 1" e un'altra riga per ogni sottotitolo.
// Se RunSubentriesOnSameLine è true, la tabella INDEX creerà una riga
// voce che racchiude l'intestazione e ogni sottotitolo.
builder.InsertBreak(BreakType.PageBreak);
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Heading 1:Subheading 1";

Assert.AreEqual(" XE  \"Heading 1:Subheading 1\"", indexEntry.GetFieldCode());

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Heading 1:Subheading 2";

doc.UpdateFields();
doc.Save(ArtifactsDir + $"Field.INDEX.XE.Subheading.docx");
```

### Guarda anche

* class [FieldIndex](../)
* spazio dei nomi [Aspose.Words.Fields](../../fieldindex/)
* assemblea [Aspose.Words](../../../)


