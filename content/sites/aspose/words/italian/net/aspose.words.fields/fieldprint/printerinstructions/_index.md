---
title: FieldPrint.PrinterInstructions
second_title: Aspose.Words per .NET API Reference
description: FieldPrint proprietà. Ottiene o imposta i caratteri del codice di controllo specifici della stampante o le istruzioni PostScript.
type: docs
weight: 30
url: /it/net/aspose.words.fields/fieldprint/printerinstructions/
---
## FieldPrint.PrinterInstructions property

Ottiene o imposta i caratteri del codice di controllo specifici della stampante o le istruzioni PostScript.

```csharp
public string PrinterInstructions { get; set; }
```

### Esempi

Mostra per inserire un campo PRINT.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("My paragraph");

// Il campo STAMPA può inviare istruzioni alla stampante.
FieldPrint field = (FieldPrint)builder.InsertField(FieldType.FieldPrint, true);

// Imposta l'area su cui la stampante esegue le istruzioni.
// In questo caso, sarà il paragrafo che contiene il nostro campo PRINT.
field.PostScriptGroup = "para";

// Quando utilizziamo una stampante che supporta PostScript per stampare il nostro documento,
// questo comando renderà bianca l'intera area specificata in "field.PostScriptGroup".
field.PrinterInstructions = "erasepage";

Assert.AreEqual(" PRINT  erasepage \\p para", field.GetFieldCode());

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.PRINT.docx");
```

### Guarda anche

* class [FieldPrint](../)
* spazio dei nomi [Aspose.Words.Fields](../../fieldprint/)
* assemblea [Aspose.Words](../../../)


