---
title: Class FieldPrint
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Fields.FieldPrint classe. Implementa il campo PRINT.
type: docs
weight: 2130
url: /it/net/aspose.words.fields/fieldprint/
---
## FieldPrint class

Implementa il campo PRINT.

```csharp
public class FieldPrint : Field
```

## Costruttori

| Nome | Descrizione |
| --- | --- |
| [FieldPrint](fieldprint/)() | Default_Costruttore |

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [DisplayResult](../../aspose.words.fields/field/displayresult/) { get; } | Ottiene il testo che rappresenta il risultato del campo visualizzato. |
| [End](../../aspose.words.fields/field/end/) { get; } | Ottiene il nodo che rappresenta la fine del campo. |
| [Format](../../aspose.words.fields/field/format/) { get; } | Ottiene a[`FieldFormat`](../fieldformat/) oggetto che fornisce l'accesso digitato alla formattazione del campo. |
| [IsDirty](../../aspose.words.fields/field/isdirty/) { get; set; } | Ottiene o imposta se il risultato corrente del campo non è più corretto (obsoleto) a causa di altre modifiche apportate al documento. |
| [IsLocked](../../aspose.words.fields/field/islocked/) { get; set; } | Ottiene o imposta se il campo è bloccato (non dovrebbe ricalcolarne il risultato). |
| [LocaleId](../../aspose.words.fields/field/localeid/) { get; set; } | Ottiene o imposta l'LCID del campo. |
| [PostScriptGroup](../../aspose.words.fields/fieldprint/postscriptgroup/) { get; set; } | Ottiene o imposta il rettangolo di disegno su cui operano le istruzioni PostScript. |
| [PrinterInstructions](../../aspose.words.fields/fieldprint/printerinstructions/) { get; set; } | Ottiene o imposta i caratteri del codice di controllo specifici della stampante o le istruzioni PostScript. |
| [Result](../../aspose.words.fields/field/result/) { get; set; } | Ottiene o imposta il testo che si trova tra il separatore di campo e la fine del campo. |
| [Separator](../../aspose.words.fields/field/separator/) { get; } | Ottiene il nodo che rappresenta il separatore di campo. Può essere nullo. |
| [Start](../../aspose.words.fields/field/start/) { get; } | Ottiene il nodo che rappresenta l'inizio del campo. |
| virtual [Type](../../aspose.words.fields/field/type/) { get; } | Ottiene il tipo di campo di Microsoft Word. |

## Metodi

| Nome | Descrizione |
| --- | --- |
| [GetFieldCode](../../aspose.words.fields/field/getfieldcode/)() | Restituisce il testo tra l'inizio del campo e il separatore di campo (o la fine del campo se non è presente alcun separatore). Sono inclusi sia il codice campo che il risultato campo dei campi figlio. |
| [GetFieldCode](../../aspose.words.fields/field/getfieldcode/)(bool) | Restituisce il testo tra l'inizio del campo e il separatore di campo (o la fine del campo se non c'è un separatore). |
| [Remove](../../aspose.words.fields/field/remove/)() | Rimuove il campo dal documento. Restituisce un nodo subito dopo il campo. Se la fine del campo è l'ultimo figlio del suo nodo padre, restituisce il suo paragrafo padre. Se il campo è già stato rimosso, ritorna **nullo** . |
| [Unlink](../../aspose.words.fields/field/unlink/)() | Esegue lo scollegamento del campo. |
| [Update](../../aspose.words.fields/field/update/)() | Esegue l'aggiornamento del campo. Genera se il campo è già in fase di aggiornamento. |
| [Update](../../aspose.words.fields/field/update/)(bool) | Esegue un aggiornamento del campo. Genera se il campo è già in fase di aggiornamento. |

### Osservazioni

Un'istruzione per inviare i caratteri del codice di controllo specifico della stampante alla stampante selezionata quando il documento viene stampato.

### Esempi

Mostra per inserire un campo PRINT.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("My paragraph");

// Il campo STAMPA può inviare istruzioni alla stampante.
FieldPrint field = (FieldPrint)builder.InsertField(FieldType.FieldPrint, true);

// Imposta l'area su cui la stampante esegue le istruzioni.
// In questo caso, sarà il paragrafo che contiene il nostro campo PRINT.
field.PostScriptGroup = "para";

// Quando utilizziamo una stampante che supporta PostScript per stampare il nostro documento,
// questo comando renderà bianca l'intera area specificata in "field.PostScriptGroup".
field.PrinterInstructions = "erasepage";

Assert.AreEqual(" PRINT  erasepage \\p para", field.GetFieldCode());

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.PRINT.docx");
```

### Guarda anche

* class [Field](../field/)
* spazio dei nomi [Aspose.Words.Fields](../../aspose.words.fields/)
* assemblea [Aspose.Words](../../)


