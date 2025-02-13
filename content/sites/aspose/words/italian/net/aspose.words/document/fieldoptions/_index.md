---
title: Document.FieldOptions
second_title: Aspose.Words per .NET API Reference
description: Document proprietà. Ottiene a Opzioni di campooggetto che rappresenta le opzioni per controllare la gestione dei campi nel documento.
type: docs
weight: 120
url: /it/net/aspose.words/document/fieldoptions/
---
## Document.FieldOptions property

Ottiene a **Opzioni di campo**oggetto che rappresenta le opzioni per controllare la gestione dei campi nel documento.

```csharp
public FieldOptions FieldOptions { get; }
```

### Esempi

Mostra come specificare l'origine delle impostazioni cultura utilizzate per la formattazione della data durante un aggiornamento del campo o la stampa unione.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserisce due campi di unione con la lingua tedesca.
builder.Font.LocaleId = new CultureInfo("de-DE").LCID;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

// Imposta le impostazioni cultura correnti sull'inglese americano dopo aver conservato il suo valore originale in una variabile.
CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("en-US");

// Questa unione utilizzerà le impostazioni cultura del thread corrente per formattare la data, in inglese americano.
doc.MailMerge.Execute(new[] { "Date1" }, new object[] { new DateTime(2020, 1, 01) });

// Configura l'unione successiva per ottenere il valore delle impostazioni cultura dal codice del campo. Il valore di quella cultura sarà tedesco.
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.MailMerge.Execute(new[] { "Date2" }, new object[] { new DateTime(2020, 1, 01) });

// Il primo risultato di unione contiene una data formattata in inglese, mentre il secondo è in tedesco.
Assert.AreEqual("Wednesday, 1 January 2020 - Mittwoch, 1 Januar 2020", doc.Range.Text.Trim());

// Ripristina le impostazioni cultura originali del thread.
Thread.CurrentThread.CurrentCulture = currentCulture;
```

### Guarda anche

* class [FieldOptions](../../../aspose.words.fields/fieldoptions/)
* class [Document](../)
* spazio dei nomi [Aspose.Words](../../document/)
* assemblea [Aspose.Words](../../../)


