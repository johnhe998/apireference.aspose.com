---
title: Class FieldDatabase
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Fields.FieldDatabase classe. Implementa il campo DATABASE.
type: docs
weight: 1590
url: /it/net/aspose.words.fields/fielddatabase/
---
## FieldDatabase class

Implementa il campo DATABASE.

```csharp
public class FieldDatabase : Field
```

## Costruttori

| Nome | Descrizione |
| --- | --- |
| [FieldDatabase](fielddatabase/)() | Default_Costruttore |

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [Connection](../../aspose.words.fields/fielddatabase/connection/) { get; set; } | Ottiene o imposta una connessione ai dati. |
| [DisplayResult](../../aspose.words.fields/field/displayresult/) { get; } | Ottiene il testo che rappresenta il risultato del campo visualizzato. |
| [End](../../aspose.words.fields/field/end/) { get; } | Ottiene il nodo che rappresenta la fine del campo. |
| [FileName](../../aspose.words.fields/fielddatabase/filename/) { get; set; } | Ottiene o imposta il percorso completo e il nome file del database |
| [FirstRecord](../../aspose.words.fields/fielddatabase/firstrecord/) { get; set; } | Ottiene o imposta il numero di record integrale del primo record di dati da inserire. |
| [Format](../../aspose.words.fields/field/format/) { get; } | Ottiene a[`FieldFormat`](../fieldformat/) oggetto che fornisce l'accesso digitato alla formattazione del campo. |
| [FormatAttributes](../../aspose.words.fields/fielddatabase/formatattributes/) { get; set; } | Ottiene o imposta quali attributi del formato devono essere applicati alla tabella. |
| [InsertHeadings](../../aspose.words.fields/fielddatabase/insertheadings/) { get; set; } | Ottiene o imposta se inserire i nomi dei campi dal database come intestazioni di colonna in la tabella risultante. |
| [InsertOnceOnMailMerge](../../aspose.words.fields/fielddatabase/insertonceonmailmerge/) { get; set; } | Ottiene o imposta se inserire dati all'inizio di un'unione. |
| [IsDirty](../../aspose.words.fields/field/isdirty/) { get; set; } | Ottiene o imposta se il risultato corrente del campo non è più corretto (obsoleto) a causa di altre modifiche apportate al documento. |
| [IsLocked](../../aspose.words.fields/field/islocked/) { get; set; } | Ottiene o imposta se il campo è bloccato (non dovrebbe ricalcolarne il risultato). |
| [LastRecord](../../aspose.words.fields/fielddatabase/lastrecord/) { get; set; } | Ottiene o imposta il numero del record integrale dell'ultimo record di dati da inserire. |
| [LocaleId](../../aspose.words.fields/field/localeid/) { get; set; } | Ottiene o imposta l'LCID del campo. |
| [Query](../../aspose.words.fields/fielddatabase/query/) { get; set; } | Ottiene o imposta una serie di istruzioni SQL che interrogano il database. |
| [Result](../../aspose.words.fields/field/result/) { get; set; } | Ottiene o imposta il testo che si trova tra il separatore di campo e la fine del campo. |
| [Separator](../../aspose.words.fields/field/separator/) { get; } | Ottiene il nodo che rappresenta il separatore di campo. Può essere nullo. |
| [Start](../../aspose.words.fields/field/start/) { get; } | Ottiene il nodo che rappresenta l'inizio del campo. |
| [TableFormat](../../aspose.words.fields/fielddatabase/tableformat/) { get; set; } | Ottiene o imposta il formato da applicare al risultato della query del database. |
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

Inserisce i risultati di una query di database in una tabella WordprocessingML.

### Esempi

Mostra come estrarre i dati da un database e inserirli come campo in un documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Questo campo DATABASE eseguirà una query su un database e visualizzerà il risultato in una tabella.
FieldDatabase field = (FieldDatabase)builder.InsertField(FieldType.FieldDatabase, true);
field.FileName = MyDir + @"Database\Northwind.mdb";
field.Connection = "DSN=MS Access Databases";
field.Query = "SELECT * FROM [Products]";

Assert.AreEqual($" DATABASE  \\d \"{DatabaseDir.Replace("\\", "\\\\") + "Northwind.mdb"}\" \\c \"DSN=MS Access Databases\" \\s \"SELECT * FROM [Products]\"", 
    field.GetFieldCode());

// Inserisce un altro campo DATABASE con una query più complessa che ordina tutti i prodotti in ordine decrescente in base alle vendite lorde.
field = (FieldDatabase)builder.InsertField(FieldType.FieldDatabase, true);
field.FileName = MyDir + @"Database\Northwind.mdb";
field.Connection = "DSN=MS Access Databases";
field.Query =
    "SELECT [Products].ProductName, FORMAT(SUM([Order Details].UnitPrice * (1 - [Order Details].Discount) * [Order Details].Quantity), 'Currency') AS GrossSales " +
    "FROM([Products] " +
    "LEFT JOIN[Order Details] ON[Products].[ProductID] = [Order Details].[ProductID]) " +
    "GROUP BY[Products].ProductName " +
    "ORDER BY SUM([Order Details].UnitPrice* (1 - [Order Details].Discount) * [Order Details].Quantity) DESC";

// Queste proprietà hanno la stessa funzione delle clausole LIMIT e TOP.
// Configurali per visualizzare solo le righe da 1 a 10 del risultato della query nella tabella del campo.
field.FirstRecord = "1";
field.LastRecord = "10";

// Questa proprietà è l'indice del formato che vogliamo usare per la nostra tabella. L'elenco dei formati di tabella si trova nel menu "Formattazione automatica tabella..."
// che appare quando creiamo un campo DATABASE in Microsoft Word. L'indice #10 corrisponde al formato "Colorful 3".
field.TableFormat = "10";

// La proprietà FormatAttribute è una rappresentazione di stringa di un numero intero che memorizza più flag.
// Possiamo applicare in modo patriarcale il formato a cui punta la proprietà TableFormat impostando diversi flag in questa proprietà.
// Il numero che utilizziamo è la somma di una combinazione di valori corrispondenti a diversi aspetti dello stile della tabella.
// 63 rappresenta 1 (bordi) + 2 (ombreggiatura) + 4 (carattere) + 8 (colore) + 16 (adattamento automatico) + 32 (righe di intestazione).
field.FormatAttributes = "63";
field.InsertHeadings = true;
field.InsertOnceOnMailMerge = true;

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.DATABASE.docx");
```

### Guarda anche

* class [Field](../field/)
* spazio dei nomi [Aspose.Words.Fields](../../aspose.words.fields/)
* assemblea [Aspose.Words](../../)


