---
title: FieldIf.FalseText
second_title: Référence de l'API Aspose.Words pour .NET
description: FieldIf propriété. Obtient ou définit le texte affiché si lexpression de comparaison est fausse.
type: docs
weight: 30
url: /fr/net/aspose.words.fields/fieldif/falsetext/
---
## FieldIf.FalseText property

Obtient ou définit le texte affiché si l'expression de comparaison est fausse.

```csharp
public string FalseText { get; set; }
```

### Exemples

Montre comment insérer un champ IF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Statement 1: ");
FieldIf field = (FieldIf)builder.InsertField(FieldType.FieldIf, true);
field.LeftExpression = "0";
field.ComparisonOperator = "=";
field.RightExpression = "1";

// Le champ IF affichera une chaîne provenant soit de sa propriété "TrueText",
// ou sa propriété "FalseText", selon la vérité de l'énoncé que nous avons construit.
field.TrueText = "True";
field.FalseText = "False";
field.Update();

// Dans ce cas, "0 = 1" est incorrect, donc le résultat affiché sera "False".
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

// Cette fois, la déclaration est correcte, donc le résultat affiché sera "True".
Assert.AreEqual(" IF  5 = \"2 + 3\" True False", field.GetFieldCode());
Assert.AreEqual(FieldIfComparisonResult.True, field.EvaluateCondition());
Assert.AreEqual("True", field.Result);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.IF.docx");
```

### Voir également

* class [FieldIf](../)
* espace de noms [Aspose.Words.Fields](../../fieldif/)
* Assemblée [Aspose.Words](../../../)


