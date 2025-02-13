---
title: Field.GetFieldCode
second_title: Aspose.Words per .NET API Reference
description: Field metodo. Restituisce il testo tra linizio del campo e il separatore di campo o la fine del campo se non è presente alcun separatore. Sono inclusi sia il codice campo che il risultato campo dei campi figlio.
type: docs
weight: 110
url: /it/net/aspose.words.fields/field/getfieldcode/
---
## GetFieldCode() {#getfieldcode}

Restituisce il testo tra l'inizio del campo e il separatore di campo (o la fine del campo se non è presente alcun separatore). Sono inclusi sia il codice campo che il risultato campo dei campi figlio.

```csharp
public string GetFieldCode()
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

Mostra come ottenere il codice di campo di un campo.

```csharp
// Apre un documento che contiene un MERGEFIELD all'interno di un campo IF.
Document doc = new Document(MyDir + "Nested fields.docx");
FieldIf fieldIf = (FieldIf)doc.Range.Fields[0];

// Esistono due modi per ottenere il codice di campo di un campo:
// 1 - Ometti i suoi campi interni:
Assert.AreEqual(" IF  > 0 \" (surplus of ) \" \"\" ", fieldIf.GetFieldCode(false));

// 2 - Includi i suoi campi interni:
Assert.AreEqual($" IF \u0013 MERGEFIELD NetIncome \u0014\u0015 > 0 \" (surplus of \u0013 MERGEFIELD  NetIncome \\f $ \u0014\u0015) \" \"\" ",
    fieldIf.GetFieldCode(true));

// Per impostazione predefinita, il metodo GetFieldCode visualizza i campi interni.
Assert.AreEqual(fieldIf.GetFieldCode(), fieldIf.GetFieldCode(true));
```

### Guarda anche

* class [Field](../)
* spazio dei nomi [Aspose.Words.Fields](../../field/)
* assemblea [Aspose.Words](../../../)

---

## GetFieldCode(bool) {#getfieldcode_1}

Restituisce il testo tra l'inizio del campo e il separatore di campo (o la fine del campo se non c'è un separatore).

```csharp
public string GetFieldCode(bool includeChildFieldCodes)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| includeChildFieldCodes | Boolean | `Vero` se devono essere inclusi i codici di campo figlio. |

### Esempi

Mostra come ottenere il codice di campo di un campo.

```csharp
// Apre un documento che contiene un MERGEFIELD all'interno di un campo IF.
Document doc = new Document(MyDir + "Nested fields.docx");
FieldIf fieldIf = (FieldIf)doc.Range.Fields[0];

// Esistono due modi per ottenere il codice di campo di un campo:
// 1 - Ometti i suoi campi interni:
Assert.AreEqual(" IF  > 0 \" (surplus of ) \" \"\" ", fieldIf.GetFieldCode(false));

// 2 - Includi i suoi campi interni:
Assert.AreEqual($" IF \u0013 MERGEFIELD NetIncome \u0014\u0015 > 0 \" (surplus of \u0013 MERGEFIELD  NetIncome \\f $ \u0014\u0015) \" \"\" ",
    fieldIf.GetFieldCode(true));

// Per impostazione predefinita, il metodo GetFieldCode visualizza i campi interni.
Assert.AreEqual(fieldIf.GetFieldCode(), fieldIf.GetFieldCode(true));
```

### Guarda anche

* class [Field](../)
* spazio dei nomi [Aspose.Words.Fields](../../field/)
* assemblea [Aspose.Words](../../../)


