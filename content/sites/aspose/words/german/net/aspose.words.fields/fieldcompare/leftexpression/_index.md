---
title: FieldCompare.LeftExpression
second_title: Aspose.Words für .NET-API-Referenz
description: FieldCompare eigendom. Ruft den linken Teil des Vergleichsausdrucks ab oder legt ihn fest.
type: docs
weight: 30
url: /de/net/aspose.words.fields/fieldcompare/leftexpression/
---
## FieldCompare.LeftExpression property

Ruft den linken Teil des Vergleichsausdrucks ab oder legt ihn fest.

```csharp
public string LeftExpression { get; set; }
```

### Beispiele

Zeigt, wie Ausdrücke mit einem COMPARE-Feld verglichen werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

FieldCompare field = (FieldCompare)builder.InsertField(FieldType.FieldCompare, true);
field.LeftExpression = "3";
field.ComparisonOperator = "<";
field.RightExpression = "2";
field.Update();

// Das COMPARE-Feld zeigt eine "0" oder eine "1" an, abhängig von der Wahrheit seiner Aussage.
// Das Ergebnis dieser Anweisung ist falsch, sodass dieses Feld eine "0" anzeigt.
Assert.AreEqual(" COMPARE  3 < 2", field.GetFieldCode());
Assert.AreEqual("0", field.Result);

builder.Writeln();

field = (FieldCompare)builder.InsertField(FieldType.FieldCompare, true);
field.LeftExpression = "5";
field.ComparisonOperator = "=";
field.RightExpression = "2 + 3";
field.Update();

// Dieses Feld zeigt eine "1" an, da die Aussage wahr ist.
Assert.AreEqual(" COMPARE  5 = \"2 + 3\"", field.GetFieldCode());
Assert.AreEqual("1", field.Result);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.COMPARE.docx");
```

### Siehe auch

* class [FieldCompare](../)
* namensraum [Aspose.Words.Fields](../../fieldcompare/)
* Montage [Aspose.Words](../../../)


