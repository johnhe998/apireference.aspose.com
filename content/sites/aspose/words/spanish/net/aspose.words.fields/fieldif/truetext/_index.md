---
title: FieldIf.TrueText
second_title: Referencia de API de Aspose.Words para .NET
description: FieldIf propiedad. Obtiene o establece el texto que se muestra si la expresión de comparación es verdadera.
type: docs
weight: 60
url: /es/net/aspose.words.fields/fieldif/truetext/
---
## FieldIf.TrueText property

Obtiene o establece el texto que se muestra si la expresión de comparación es verdadera.

```csharp
public string TrueText { get; set; }
```

### Ejemplos

Muestra cómo insertar un campo IF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Statement 1: ");
FieldIf field = (FieldIf)builder.InsertField(FieldType.FieldIf, true);
field.LeftExpression = "0";
field.ComparisonOperator = "=";
field.RightExpression = "1";

// El campo IF mostrará una cadena de su propiedad "TrueText",
// o su propiedad "FalseText", dependiendo de la verdad del enunciado que hayamos construido.
field.TrueText = "True";
field.FalseText = "False";
field.Update();

// En este caso, "0 = 1" es incorrecto, por lo que el resultado mostrado será "Falso".
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

// Esta vez la afirmación es correcta, por lo que el resultado mostrado será "Verdadero".
Assert.AreEqual(" IF  5 = \"2 + 3\" True False", field.GetFieldCode());
Assert.AreEqual(FieldIfComparisonResult.True, field.EvaluateCondition());
Assert.AreEqual("True", field.Result);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.IF.docx");
```

### Ver también

* class [FieldIf](../)
* espacio de nombres [Aspose.Words.Fields](../../fieldif/)
* asamblea [Aspose.Words](../../../)


