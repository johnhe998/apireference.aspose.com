---
title: Range.UpdateFields
second_title: Aspose.Words per .NET API Reference
description: Range metodo. Aggiorna i valori dei campi del documento in questo intervallo.
type: docs
weight: 110
url: /it/net/aspose.words/range/updatefields/
---
## Range.UpdateFields method

Aggiorna i valori dei campi del documento in questo intervallo.

```csharp
public void UpdateFields()
```

### Osservazioni

Quando apri, modifichi e quindi salvi un documento, Aspose.Words non aggiorna i campi automaticamente, li mantiene intatti. Pertanto, di solito dovresti chiamare questo metodo prima di salvare se hai modificato il documento a livello di codice e vuoi assicurarti i valori di campo (calcolati) corretti vengono visualizzati nel documento salvato.

Non è necessario aggiornare i campi dopo aver eseguito una stampa unione perché la stampa unione è una specie di campo update e aggiorna automaticamente tutti i campi nel documento.

Questo metodo non aggiorna tutti i tipi di campo. Per l'elenco dettagliato dei tipi di campo supportati, vedere la Guida per i programmatori.

Questo metodo non aggiorna i campi relativi agli algoritmi di layout di pagina (ad es. PAGE, PAGES, PAGEREF). I campi relativi al layout di pagina vengono aggiornati quando si esegue il rendering di un documento o si chiama[`UpdatePageLayout`](../../document/updatepagelayout/).

Per aggiornare i campi nell'intero documento utilizzare[`UpdateFields`](../../document/updatefields/).

### Esempi

Mostra come aggiornare tutti i campi in un intervallo.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(" DOCPROPERTY Category");
builder.InsertBreak(BreakType.SectionBreakEvenPage);
builder.InsertField(" DOCPROPERTY Category");

// I campi DOCPROPERTY sopra visualizzeranno il valore di questa proprietà del documento incorporata.
doc.BuiltInDocumentProperties.Category = "MyCategory";

// Se aggiorniamo il valore di una proprietà del documento, dovremo aggiornare tutti i campi DOCPROPERTY per visualizzarlo.
Assert.AreEqual(string.Empty, doc.Range.Fields[0].Result);
Assert.AreEqual(string.Empty, doc.Range.Fields[1].Result);

// Aggiorna tutti i campi che si trovano nell'intervallo della prima sezione.
doc.FirstSection.Range.UpdateFields();

Assert.AreEqual("MyCategory", doc.Range.Fields[0].Result);
Assert.AreEqual(string.Empty, doc.Range.Fields[1].Result);
```

### Guarda anche

* class [Range](../)
* spazio dei nomi [Aspose.Words](../../range/)
* assemblea [Aspose.Words](../../../)


