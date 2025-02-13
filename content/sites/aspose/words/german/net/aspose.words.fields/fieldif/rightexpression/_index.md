---
title: FieldIf.RightExpression
second_title: Aspose.Words für .NET-API-Referenz
description: FieldIf eigendom. Holt oder setzt den rechten Teil des Vergleichsausdrucks.
type: docs
weight: 50
url: /de/net/aspose.words.fields/fieldif/rightexpression/
---
## FieldIf.RightExpression property

Holt oder setzt den rechten Teil des Vergleichsausdrucks.

```csharp
public string RightExpression { get; set; }
```

### Beispiele

Zeigt, wie ein IF-Feld eingefügt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Statement 1: ");
FieldIf field = (FieldIf)builder.InsertField(FieldType.FieldIf, true);
field.LeftExpression = "0";
field.ComparisonOperator = "=";
field.RightExpression = "1";

// Das IF-Feld zeigt einen String entweder aus seiner "TrueText"-Eigenschaft,
// oder seine "FalseText"-Eigenschaft, abhängig von der Wahrheit der von uns konstruierten Aussage.
field.TrueText = "True";
field.FalseText = "False";
field.Update();

// In diesem Fall ist "0 = 1" falsch, daher ist das angezeigte Ergebnis "False".
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

// Diesmal ist die Aussage richtig, also ist das angezeigte Ergebnis "True".
Assert.AreEqual(" IF  5 = \"2 + 3\" True False", field.GetFieldCode());
Assert.AreEqual(FieldIfComparisonResult.True, field.EvaluateCondition());
Assert.AreEqual("True", field.Result);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.IF.docx");
```

### Siehe auch

* class [FieldIf](../)
* namensraum [Aspose.Words.Fields](../../fieldif/)
* Montage [Aspose.Words](../../../)


