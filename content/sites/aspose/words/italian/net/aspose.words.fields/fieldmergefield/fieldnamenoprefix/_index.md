---
title: FieldMergeField.FieldNameNoPrefix
second_title: Aspose.Words per .NET API Reference
description: FieldMergeField proprietà. Restituisce solo il nome del campo dati. Qualsiasi prefisso viene rimosso nella proprietà del prefisso.
type: docs
weight: 20
url: /it/net/aspose.words.fields/fieldmergefield/fieldnamenoprefix/
---
## FieldMergeField.FieldNameNoPrefix property

Restituisce solo il nome del campo dati. Qualsiasi prefisso viene rimosso nella proprietà del prefisso.

```csharp
public string FieldNameNoPrefix { get; }
```

### Esempi

Mostra come utilizzare i campi MERGEFIELD per eseguire una stampa unione.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crea una tabella di dati da utilizzare come origine dati per la stampa unione.
DataTable table = new DataTable("Employees");
table.Columns.Add("Courtesy Title");
table.Columns.Add("First Name");
table.Columns.Add("Last Name");
table.Rows.Add("Mr.", "John", "Doe");
table.Rows.Add("Mrs.", "Jane", "Cardholder");

// Inserisce un MERGEFIELD con una proprietà FieldName impostata sul nome di una colonna nell'origine dati.
FieldMergeField fieldMergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
fieldMergeField.FieldName = "Courtesy Title";
fieldMergeField.IsMapped = true;
fieldMergeField.IsVerticalFormatting = false;

// Possiamo applicare il testo prima e dopo il valore che questo campo accetta quando avviene l'unione.
fieldMergeField.TextBefore = "Dear ";
fieldMergeField.TextAfter = " ";

Assert.AreEqual(" MERGEFIELD  \"Courtesy Title\" \\m \\b \"Dear \" \\f \" \"", fieldMergeField.GetFieldCode());

// Inserisce un altro MERGEFIELD per una colonna diversa nell'origine dati.
fieldMergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
fieldMergeField.FieldName = "Last Name";
fieldMergeField.TextAfter = ":";

doc.UpdateFields();
doc.MailMerge.Execute(table);

Assert.AreEqual("Dear Mr. Doe:\u000cDear Mrs. Cardholder:", doc.GetText().Trim());
```

### Guarda anche

* class [FieldMergeField](../)
* spazio dei nomi [Aspose.Words.Fields](../../fieldmergefield/)
* assemblea [Aspose.Words](../../../)


