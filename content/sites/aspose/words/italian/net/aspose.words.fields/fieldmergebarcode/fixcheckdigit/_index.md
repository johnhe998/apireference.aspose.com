---
title: FieldMergeBarcode.FixCheckDigit
second_title: Aspose.Words per .NET API Reference
description: FieldMergeBarcode proprietà. Ottiene o imposta se correggere la cifra di controllo se non è valida.
type: docs
weight: 90
url: /it/net/aspose.words.fields/fieldmergebarcode/fixcheckdigit/
---
## FieldMergeBarcode.FixCheckDigit property

Ottiene o imposta se correggere la cifra di controllo se non è valida.

```csharp
public bool FixCheckDigit { get; set; }
```

### Esempi

Mostra come eseguire una stampa unione su codici a barre EAN13.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserisce un campo MERGEBARCCODE, che accetterà i valori da un'origine dati durante una stampa unione.
// Questo campo converte tutti i valori nella colonna "MyEAN13Barcode" di un'origine dati di unione in codici a barre EAN13.
FieldMergeBarcode field = (FieldMergeBarcode)builder.InsertField(FieldType.FieldMergeBarcode, true);
field.BarcodeType = "EAN13";
field.BarcodeValue = "MyEAN13Barcode";

// Visualizza il valore numerico del codice a barre sotto le barre.
field.DisplayText = true;
field.PosCodeStyle = "CASE";
field.FixCheckDigit = true;

Assert.AreEqual(FieldType.FieldMergeBarcode, field.Type);
Assert.AreEqual(" MERGEBARCODE  MyEAN13Barcode EAN13 \\t \\p CASE \\x", field.GetFieldCode());
builder.Writeln();

// Crea una DataTable con una colonna con lo stesso nome del nostro campo MERGEBARCODE BarcodeValue.
// La stampa unione creerà una nuova pagina per ogni riga. Ogni pagina conterrà un campo DISPLAYBARCCODE,
// che visualizzerà un codice a barre EAN13 con il valore della riga unita.
DataTable table = new DataTable("Barcodes");
table.Columns.Add("MyEAN13Barcode");
table.Rows.Add(new[] { "501234567890" });
table.Rows.Add(new[] { "123456789012" });

doc.MailMerge.Execute(table);

Assert.AreEqual(FieldType.FieldDisplayBarcode, doc.Range.Fields[0].Type);
Assert.AreEqual("DISPLAYBARCODE \"501234567890\" EAN13 \\t \\p CASE \\x",
    doc.Range.Fields[0].GetFieldCode());
Assert.AreEqual(FieldType.FieldDisplayBarcode, doc.Range.Fields[1].Type);
Assert.AreEqual("DISPLAYBARCODE \"123456789012\" EAN13 \\t \\p CASE \\x",
    doc.Range.Fields[1].GetFieldCode());

doc.Save(ArtifactsDir + "Field.MERGEBARCODE.EAN13.docx");
```

### Guarda anche

* class [FieldMergeBarcode](../)
* spazio dei nomi [Aspose.Words.Fields](../../fieldmergebarcode/)
* assemblea [Aspose.Words](../../../)


