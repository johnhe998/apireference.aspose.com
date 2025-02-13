---
title: FieldGreetingLine.NameFormat
second_title: Aspose.Words per .NET API Reference
description: FieldGreetingLine proprietà. Ottiene o imposta il formato del nome incluso nel campo.
type: docs
weight: 40
url: /it/net/aspose.words.fields/fieldgreetingline/nameformat/
---
## FieldGreetingLine.NameFormat property

Ottiene o imposta il formato del nome incluso nel campo.

```csharp
public string NameFormat { get; set; }
```

### Esempi

Mostra come inserire un campo GREETINGLINE.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crea un saluto generico utilizzando un campo GREETINGLINE e del testo dopo di esso.
FieldGreetingLine field = (FieldGreetingLine)builder.InsertField(FieldType.FieldGreetingLine, true);
builder.Writeln("\n\n\tThis is your custom greeting, created programmatically using Aspose Words!");

// Un campo GREETINGLINE accetta valori da un'origine dati durante una stampa unione, come un MERGEFIELD.
// Può anche formattare il modo in cui i dati dell'origine vengono scritti al suo posto una volta completata la stampa unione.
// La raccolta dei nomi dei campi corrisponde alle colonne dell'origine dati
// da cui il campo prenderà i valori.
Assert.AreEqual(0, field.GetFieldNames().Length);

// Per popolare quell'array, dobbiamo specificare un formato per la nostra linea di saluto.
field.NameFormat = "<< _BEFORE_ Dear >><< _TITLE0_ >><< _LAST0_ >><< _AFTER_ ,>> ";

// Ora, il nostro campo accetterà i valori di queste due colonne nell'origine dati.
Assert.AreEqual("Courtesy Title", field.GetFieldNames()[0]);
Assert.AreEqual("Last Name", field.GetFieldNames()[1]);
Assert.AreEqual(2, field.GetFieldNames().Length);

// Questa stringa coprirà tutti i casi in cui i dati della tabella di dati non sono validi
// sostituendo il nome non corretto con una stringa.
field.AlternateText = "Sir or Madam";

// Imposta una lingua per formattare il risultato.
field.LanguageId = new CultureInfo("en-US").LCID.ToString();

Assert.AreEqual(" GREETINGLINE  \\f \"<< _BEFORE_ Dear >><< _TITLE0_ >><< _LAST0_ >><< _AFTER_ ,>> \" \\e \"Sir or Madam\" \\l 1033", 
    field.GetFieldCode());

// Crea una tabella di dati con colonne i cui nomi corrispondono agli elementi
// dalla raccolta dei nomi dei campi del campo, quindi eseguire la stampa unione.
DataTable table = new DataTable("Employees");
table.Columns.Add("Courtesy Title");
table.Columns.Add("First Name");
table.Columns.Add("Last Name");
table.Rows.Add("Mr.", "John", "Doe");
table.Rows.Add("Mrs.", "Jane", "Cardholder");

// Questa riga ha un valore non valido nella colonna del titolo di cortesia, quindi il nostro saluto verrà impostato automaticamente sul testo alternativo.
table.Rows.Add("", "No", "Name");

doc.MailMerge.Execute(table);

Assert.That(doc.Range.Fields, Is.Empty);
Assert.AreEqual("Dear Mr. Doe,\r\r\tThis is your custom greeting, created programmatically using Aspose Words!\r" +
                "\fDear Mrs. Cardholder,\r\r\tThis is your custom greeting, created programmatically using Aspose Words!\r" +
                "\fDear Sir or Madam,\r\r\tThis is your custom greeting, created programmatically using Aspose Words!",
    doc.GetText().Trim());
```

### Guarda anche

* class [FieldGreetingLine](../)
* spazio dei nomi [Aspose.Words.Fields](../../fieldgreetingline/)
* assemblea [Aspose.Words](../../../)


