---
title: Field.IsLocked
second_title: Aspose.Words per .NET API Reference
description: Field proprietà. Ottiene o imposta se il campo è bloccato non dovrebbe ricalcolarne il risultato.
type: docs
weight: 50
url: /it/net/aspose.words.fields/field/islocked/
---
## Field.IsLocked property

Ottiene o imposta se il campo è bloccato (non dovrebbe ricalcolarne il risultato).

```csharp
public bool IsLocked { get; set; }
```

### Esempi

Mostra come lavorare con un nodo FieldStart.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

FieldDate field = (FieldDate)builder.InsertField(FieldType.FieldDate, true);
field.Format.DateTimeFormat = "dddd, MMMM dd, yyyy";
field.Update();

FieldChar fieldStart = field.Start;

Assert.AreEqual(FieldType.FieldDate, fieldStart.FieldType);
Assert.AreEqual(false, fieldStart.IsDirty);
Assert.AreEqual(false, fieldStart.IsLocked);

// Recupera l'oggetto facciata che rappresenta il campo nel documento.
field = (FieldDate)fieldStart.GetField();

Assert.AreEqual(false, field.IsLocked);
Assert.AreEqual(" DATE  \\@ \"dddd, MMMM dd, yyyy\"", field.GetFieldCode());

// Aggiorna il campo per mostrare la data corrente.
field.Update();
```

### Guarda anche

* class [Field](../)
* spazio dei nomi [Aspose.Words.Fields](../../field/)
* assemblea [Aspose.Words](../../../)


