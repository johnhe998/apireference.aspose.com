---
title: MailMerge.CleanupOptions
second_title: Aspose.Words per .NET API Reference
description: MailMerge proprietà. Ottiene o imposta una serie di flag che specificano quali elementi devono essere rimossi durante la stampa unione.
type: docs
weight: 10
url: /it/net/aspose.words.mailmerging/mailmerge/cleanupoptions/
---
## MailMerge.CleanupOptions property

Ottiene o imposta una serie di flag che specificano quali elementi devono essere rimossi durante la stampa unione.

```csharp
public MailMergeCleanupOptions CleanupOptions { get; set; }
```

### Esempi

Mostra come rimuovere i paragrafi vuoti che una stampa unione può creare dal documento di output dell'unione.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(" MERGEFIELD TableStart:MyTable");
builder.InsertField(" MERGEFIELD FirstName ");
builder.Write(" ");
builder.InsertField(" MERGEFIELD LastName ");
builder.InsertField(" MERGEFIELD TableEnd:MyTable");

DataTable dataTable = new DataTable("MyTable");
dataTable.Columns.Add("FirstName");
dataTable.Columns.Add("LastName");
dataTable.Rows.Add(new object[] { "John", "Doe" });
dataTable.Rows.Add(new object[] { "", "" });
dataTable.Rows.Add(new object[] { "Jane", "Doe" });

doc.MailMerge.CleanupOptions = mailMergeCleanupOptions;
doc.MailMerge.ExecuteWithRegions(dataTable);

if (doc.MailMerge.CleanupOptions == MailMergeCleanupOptions.RemoveEmptyParagraphs) 
    Assert.AreEqual(
        "John Doe\r" +
        "Jane Doe", doc.GetText().Trim());
else
    Assert.AreEqual(
        "John Doe\r" +
        " \r" +
        "Jane Doe", doc.GetText().Trim());
```

Mostra come rimuovere automaticamente i MERGEFIELD che restano inutilizzati durante la stampa unione.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crea un documento con MERGEFIELD per tre colonne di una tabella di origine dati stampa unione,
// e quindi crea una tabella con solo due colonne i cui nomi corrispondono ai nostri MERGEFIELD.
builder.InsertField(" MERGEFIELD FirstName ");
builder.Write(" ");
builder.InsertField(" MERGEFIELD LastName ");
builder.InsertParagraph();
builder.InsertField(" MERGEFIELD City ");

DataTable dataTable = new DataTable("MyTable");
dataTable.Columns.Add("FirstName");
dataTable.Columns.Add("LastName");
dataTable.Rows.Add(new object[] { "John", "Doe" });
dataTable.Rows.Add(new object[] { "Joe", "Bloggs" });

// Il nostro terzo MERGEFIELD fa riferimento a una colonna "Città", che non esiste nella nostra origine dati.
// La stampa unione lascerà intatti campi come questo nel loro stato precedente all'unione.
// L'impostazione della proprietà "CleanupOptions" su "RemoveUnusedFields" rimuoverà tutti i MERGEFIELD
// che non vengono utilizzati durante una stampa unione per ripulire i documenti di unione.
doc.MailMerge.CleanupOptions = mailMergeCleanupOptions;
doc.MailMerge.Execute(dataTable);

if (mailMergeCleanupOptions == MailMergeCleanupOptions.RemoveUnusedFields || 
    mailMergeCleanupOptions == MailMergeCleanupOptions.RemoveStaticFields)
    Assert.AreEqual(0, doc.Range.Fields.Count);
else
    Assert.AreEqual(2, doc.Range.Fields.Count);
```

### Guarda anche

* enum [MailMergeCleanupOptions](../../mailmergecleanupoptions/)
* class [MailMerge](../)
* spazio dei nomi [Aspose.Words.MailMerging](../../mailmerge/)
* assemblea [Aspose.Words](../../../)


