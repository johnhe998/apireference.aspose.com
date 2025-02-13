---
title: Field.Result
second_title: Aspose.Words per .NET API Reference
description: Field proprietà. Ottiene o imposta il testo che si trova tra il separatore di campo e la fine del campo.
type: docs
weight: 70
url: /it/net/aspose.words.fields/field/result/
---
## Field.Result property

Ottiene o imposta il testo che si trova tra il separatore di campo e la fine del campo.

```csharp
public string Result { get; set; }
```

### Esempi

Mostra come inserire un campo in un documento utilizzando un codice campo.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Field field = builder.InsertField("DATE \\@ \"dddd, MMMM dd, yyyy\"");

Assert.AreEqual(FieldType.FieldDate, field.Type);
Assert.AreEqual("DATE \\@ \"dddd, MMMM dd, yyyy\"", field.GetFieldCode());

// Questo sovraccarico del metodo InsertField aggiorna automaticamente i campi inseriti.
Assert.That(DateTime.Parse(field.Result), Is.EqualTo(DateTime.Today).Within(1).Days);
```

### Guarda anche

* class [Field](../)
* spazio dei nomi [Aspose.Words.Fields](../../field/)
* assemblea [Aspose.Words](../../../)


