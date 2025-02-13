---
title: FieldDatabase.LastRecord
second_title: Aspose.Words per .NET API Reference
description: FieldDatabase proprietà. Ottiene o imposta il numero del record integrale dellultimo record di dati da inserire.
type: docs
weight: 80
url: /it/net/aspose.words.fields/fielddatabase/lastrecord/
---
## FieldDatabase.LastRecord property

Ottiene o imposta il numero del record integrale dell'ultimo record di dati da inserire.

```csharp
public string LastRecord { get; set; }
```

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

* class [FieldDatabase](../)
* spazio dei nomi [Aspose.Words.Fields](../../fielddatabase/)
* assemblea [Aspose.Words](../../../)


