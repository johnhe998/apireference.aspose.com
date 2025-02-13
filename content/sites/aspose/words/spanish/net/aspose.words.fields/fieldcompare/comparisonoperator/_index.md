---
title: FieldCompare.ComparisonOperator
second_title: Referencia de API de Aspose.Words para .NET
description: FieldCompare propiedad. Obtiene o establece el operador de comparación.
type: docs
weight: 20
url: /es/net/aspose.words.fields/fieldcompare/comparisonoperator/
---
## FieldCompare.ComparisonOperator property

Obtiene o establece el operador de comparación.

```csharp
public string ComparisonOperator { get; set; }
```

### Ejemplos

Muestra cómo comparar expresiones utilizando un campo COMPARE.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

FieldCompare field = (FieldCompare)builder.InsertField(FieldType.FieldCompare, true);
field.LeftExpression = "3";
field.ComparisonOperator = "<";
field.RightExpression = "2";
field.Update();

// El campo COMPARE muestra un "0" o un "1", dependiendo de la veracidad de su declaración.
// El resultado de esta declaración es falso, por lo que este campo mostrará un "0".
Assert.AreEqual(" COMPARE  3 < 2", field.GetFieldCode());
Assert.AreEqual("0", field.Result);

builder.Writeln();

field = (FieldCompare)builder.InsertField(FieldType.FieldCompare, true);
field.LeftExpression = "5";
field.ComparisonOperator = "=";
field.RightExpression = "2 + 3";
field.Update();

// Este campo muestra un "1" ya que la afirmación es verdadera.
Assert.AreEqual(" COMPARE  5 = \"2 + 3\"", field.GetFieldCode());
Assert.AreEqual("1", field.Result);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.COMPARE.docx");
```

### Ver también

* class [FieldCompare](../)
* espacio de nombres [Aspose.Words.Fields](../../fieldcompare/)
* asamblea [Aspose.Words](../../../)


