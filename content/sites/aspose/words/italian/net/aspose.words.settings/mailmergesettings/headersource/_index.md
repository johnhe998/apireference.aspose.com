---
title: MailMergeSettings.HeaderSource
second_title: Aspose.Words per .NET API Reference
description: MailMergeSettings proprietà. Specifica il percorso dellorigine dellintestazione della stampa unione. Il valore predefinito è una stringa vuota.
type: docs
weight: 100
url: /it/net/aspose.words.settings/mailmergesettings/headersource/
---
## MailMergeSettings.HeaderSource property

Specifica il percorso dell'origine dell'intestazione della stampa unione. Il valore predefinito è una stringa vuota.

```csharp
public string HeaderSource { get; set; }
```

### Esempi

Mostra come costruire un'origine dati per una stampa unione da un'origine intestazione e un'origine dati.

```csharp
// Crea un file di intestazione di unione delle etichette postali, che sarà costituito da una tabella con una riga.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartTable();
builder.InsertCell();
builder.Write("FirstName");
builder.InsertCell();
builder.Write("LastName");
builder.EndTable();

doc.Save(ArtifactsDir + "MailMerge.MailingLabelMerge.Header.docx");

// Crea un file di dati di unione di etichette postali costituito da una tabella con una riga
// e lo stesso numero di colonne della tabella del documento di intestazione. 
doc = new Document();
builder = new DocumentBuilder(doc);

builder.StartTable();
builder.InsertCell();
builder.Write("John");
builder.InsertCell();
builder.Write("Doe");
builder.EndTable();

doc.Save(ArtifactsDir + "MailMerge.MailingLabelMerge.Data.docx");

// Crea un documento di destinazione di unione con MERGEFIELDS con nomi che
// abbina i nomi delle colonne nella tabella dei file di intestazione di unione.
doc = new Document();
builder = new DocumentBuilder(doc);

builder.Write("Dear ");
builder.InsertField("MERGEFIELD FirstName", "<FirstName>");
builder.Write(" ");
builder.InsertField("MERGEFIELD LastName", "<LastName>");

MailMergeSettings settings = doc.MailMergeSettings;

// Costruisci un'origine dati per la nostra stampa unione specificando due nomi di file di documenti.
// L'origine dell'intestazione nominerà le colonne della tabella dell'origine dati.
settings.HeaderSource = ArtifactsDir + "MailMerge.MailingLabelMerge.Header.docx";

// L'origine dati fornirà righe di dati per tutte le colonne nella tabella del documento di intestazione.
settings.DataSource = ArtifactsDir + "MailMerge.MailingLabelMerge.Data.docx";

// Configura un tipo di etichetta postale per la stampa unione, che verrà eseguita da Microsoft Word
// non appena lo usiamo per caricare il documento di output.
settings.Query = "SELECT * FROM " + settings.DataSource;
settings.MainDocumentType = MailMergeMainDocumentType.MailingLabels;
settings.DataType = MailMergeDataType.TextFile;
settings.LinkToQuery = true;
settings.ViewMergedData = true;

doc.Save(ArtifactsDir + "MailMerge.MailingLabelMerge.docx");
```

### Guarda anche

* class [MailMergeSettings](../)
* spazio dei nomi [Aspose.Words.Settings](../../mailmergesettings/)
* assemblea [Aspose.Words](../../../)


