---
title: Document.NormalizeFieldTypes
second_title: Aspose.Words per .NET API Reference
description: Document metodo. Modifica i valori del tipo di campoFieldType diFieldStart FieldSeparator FieldEnd nellintero documento in modo che corrispondano ai tipi di campo contenuti nei codici di campo.
type: docs
weight: 610
url: /it/net/aspose.words/document/normalizefieldtypes/
---
## Document.NormalizeFieldTypes method

Modifica i valori del tipo di campo[`FieldType`](../../../aspose.words.fields/fieldchar/fieldtype/) di[`FieldStart`](../../../aspose.words.fields/fieldstart/) ,[`FieldSeparator`](../../../aspose.words.fields/fieldseparator/) ,[`FieldEnd`](../../../aspose.words.fields/fieldend/) nell'intero documento in modo che corrispondano ai tipi di campo contenuti nei codici di campo.

```csharp
public void NormalizeFieldTypes()
```

### Osservazioni

Utilizzare questo metodo dopo le modifiche al documento che influiscono sui tipi di campo.

Per modificare i valori del tipo di campo in una parte specifica del documento, utilizzare[`NormalizeFieldTypes`](../../range/normalizefieldtypes/).

### Esempi

Mostra come mantenere aggiornato il tipo di un campo con il relativo codice di campo.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Field field = builder.InsertField("DATE", null);

// Aspose.Words rileva automaticamente i tipi di campo in base ai codici di campo.
Assert.AreEqual(FieldType.FieldDate, field.Type);

// Modifica manualmente il testo grezzo del campo, che determina il codice del campo.
Run fieldText = (Run)doc.FirstSection.Body.FirstParagraph.GetChildNodes(NodeType.Run, true)[0];

// La modifica del codice del campo ha cambiato questo campo in uno di tipo diverso,
// ma le proprietà del tipo del campo mostrano ancora il vecchio tipo.
Assert.AreEqual("PAGE", field.GetFieldCode());
Assert.AreEqual(FieldType.FieldDate, field.Type);
Assert.AreEqual(FieldType.FieldDate, field.Start.FieldType);
Assert.AreEqual(FieldType.FieldDate, field.Separator.FieldType);
Assert.AreEqual(FieldType.FieldDate, field.End.FieldType);

// Aggiorna quelle proprietà con questo metodo per visualizzare il valore corrente.
doc.NormalizeFieldTypes();

Assert.AreEqual(FieldType.FieldPage, field.Type);
Assert.AreEqual(FieldType.FieldPage, field.Start.FieldType);
Assert.AreEqual(FieldType.FieldPage, field.Separator.FieldType); 
Assert.AreEqual(FieldType.FieldPage, field.End.FieldType);
```

### Guarda anche

* class [Document](../)
* spazio dei nomi [Aspose.Words](../../document/)
* assemblea [Aspose.Words](../../../)


