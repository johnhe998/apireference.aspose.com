---
title: FieldOptions.UserPromptRespondent
second_title: Aspose.Words per .NET API Reference
description: FieldOptions proprietà. Ottiene o imposta il rispondente alle richieste dellutente durante laggiornamento del campo.
type: docs
weight: 200
url: /it/net/aspose.words.fields/fieldoptions/userpromptrespondent/
---
## FieldOptions.UserPromptRespondent property

Ottiene o imposta il rispondente alle richieste dell'utente durante l'aggiornamento del campo.

```csharp
public IFieldUserPromptRespondent UserPromptRespondent { get; set; }
```

### Osservazioni

Se il valore di questa proprietà è impostato su **nullo** , i campi che richiedono la risposta dell'utente su prompting (come[`FieldAsk`](../../fieldask/) o[`FieldFillIn`](../../fieldfillin/)) non sono aggiornati.

Il valore predefinito è **nullo**.

### Esempi

Mostra come creare un campo ASK e impostarne le proprietà.

```csharp
[Test]
public void FieldAsk()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Inserisci un campo in cui verrà inserita la risposta al nostro campo ASK.
    FieldRef fieldRef = (FieldRef)builder.InsertField(FieldType.FieldRef, true);
    fieldRef.BookmarkName = "MyAskField";
    builder.Writeln();

    Assert.AreEqual(" REF  MyAskField", fieldRef.GetFieldCode());

    // Inserisci il campo ASK e modifica le sue proprietà per fare riferimento al nostro campo REF in base al nome del segnalibro.
    FieldAsk fieldAsk = (FieldAsk)builder.InsertField(FieldType.FieldAsk, true);
    fieldAsk.BookmarkName = "MyAskField";
    fieldAsk.PromptText = "Please provide a response for this ASK field";
    fieldAsk.DefaultResponse = "Response from within the field.";
    fieldAsk.PromptOnceOnMailMerge = true;
    builder.Writeln();

    Assert.AreEqual(
        " ASK  MyAskField \"Please provide a response for this ASK field\" \\d \"Response from within the field.\" \\o",
        fieldAsk.GetFieldCode());

    // I campi ASK applicano la risposta predefinita ai rispettivi campi REF durante una stampa unione.
    DataTable table = new DataTable("My Table");
    table.Columns.Add("Column 1");
    table.Rows.Add("Row 1");
    table.Rows.Add("Row 2");

    FieldMergeField fieldMergeField = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, true);
    fieldMergeField.FieldName = "Column 1";

    // Possiamo modificare o sovrascrivere la risposta predefinita nei nostri campi ASK con un risponditore personalizzato,
    // che si verificherà durante una stampa unione.
    doc.FieldOptions.UserPromptRespondent = new MyPromptRespondent();
    doc.MailMerge.Execute(table);

    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.ASK.docx");

/// <summary>
/// Antepone il testo alla risposta predefinita di un campo ASK durante una stampa unione.
/// </summary>
private class MyPromptRespondent : IFieldUserPromptRespondent
{
    public string Respond(string promptText, string defaultResponse)
    {
        return "Response from MyPromptRespondent. " + defaultResponse;
    }
}
```

### Guarda anche

* interface [IFieldUserPromptRespondent](../../ifielduserpromptrespondent/)
* class [FieldOptions](../)
* spazio dei nomi [Aspose.Words.Fields](../../fieldoptions/)
* assemblea [Aspose.Words](../../../)


