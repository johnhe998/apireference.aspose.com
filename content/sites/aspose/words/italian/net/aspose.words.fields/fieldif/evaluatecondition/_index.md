---
title: FieldIf.EvaluateCondition
second_title: Aspose.Words per .NET API Reference
description: FieldIf metodo. Valuta la condizione.
type: docs
weight: 70
url: /it/net/aspose.words.fields/fieldif/evaluatecondition/
---
## FieldIf.EvaluateCondition method

Valuta la condizione.

```csharp
public FieldIfComparisonResult EvaluateCondition()
```

### Valore di ritorno

A[`FieldIfComparisonResult`](../../fieldifcomparisonresult/) valore che rappresenta il risultato della valutazione della condizione.

### Esempi

Mostra come inserire un campo SE.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Statement 1: ");
FieldIf field = (FieldIf)builder.InsertField(FieldType.FieldIf, true);
field.LeftExpression = "0";
field.ComparisonOperator = "=";
field.RightExpression = "1";

// Il campo SE visualizzerà una stringa dalla sua proprietà "TrueText",
// o la sua proprietà "FalseText", a seconda della verità dell'affermazione che abbiamo costruito.
field.TrueText = "True";
field.FalseText = "False";
field.Update();

// In questo caso, "0 = 1" non è corretto, quindi il risultato visualizzato sarà "False".
Assert.AreEqual(" IF  0 = 1 True False", field.GetFieldCode());
Assert.AreEqual(FieldIfComparisonResult.False, field.EvaluateCondition());
Assert.AreEqual("False", field.Result);

builder.Write("\nStatement 2: ");
field = (FieldIf)builder.InsertField(FieldType.FieldIf, true);
field.LeftExpression = "5";
field.ComparisonOperator = "=";
field.RightExpression = "2 + 3";
field.TrueText = "True";
field.FalseText = "False";
field.Update();

// Questa volta l'affermazione è corretta, quindi il risultato visualizzato sarà "True".
Assert.AreEqual(" IF  5 = \"2 + 3\" True False", field.GetFieldCode());
Assert.AreEqual(FieldIfComparisonResult.True, field.EvaluateCondition());
Assert.AreEqual("True", field.Result);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.IF.docx");
```

### Guarda anche

* enum [FieldIfComparisonResult](../../fieldifcomparisonresult/)
* class [FieldIf](../)
* spazio dei nomi [Aspose.Words.Fields](../../fieldif/)
* assemblea [Aspose.Words](../../../)


