---
title: Field.LocaleId
second_title: Aspose.Words per .NET API Reference
description: Field proprietà. Ottiene o imposta lLCID del campo.
type: docs
weight: 60
url: /it/net/aspose.words.fields/field/localeid/
---
## Field.LocaleId property

Ottiene o imposta l'LCID del campo.

```csharp
public int LocaleId { get; set; }
```

### Esempi

Mostra come inserire un campo e lavorare con la sua locale.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserisci un campo DATA, quindi stampa la data che verrà visualizzata.
// Le impostazioni cultura correnti del thread determinano la formattazione della data.
Field field = builder.InsertField(@"DATE");
Console.WriteLine($"Today's date, as displayed in the \"{CultureInfo.CurrentCulture.EnglishName}\" culture: {field.Result}");

Assert.AreEqual(1033, field.LocaleId);
// La modifica delle impostazioni cultura del nostro thread influirà sul risultato del campo DATE.
// Un altro modo per ottenere il campo DATE per visualizzare una data in una lingua diversa consiste nell'usare la relativa proprietà LocaleId.
// In questo modo è possibile evitare di modificare la cultura del thread per ottenere questo effetto.
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
CultureInfo de = new CultureInfo("de-DE");
field.LocaleId = de.LCID;
field.Update();

Console.WriteLine($"Today's date, as displayed according to the \"{CultureInfo.GetCultureInfo(field.LocaleId).EnglishName}\" culture: {field.Result}");
```

### Guarda anche

* class [Field](../)
* spazio dei nomi [Aspose.Words.Fields](../../field/)
* assemblea [Aspose.Words](../../../)


