---
title: Enum FieldIfComparisonResult
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Fields.FieldIfComparisonResult énumération. Spécifie le résultat de lévaluation de la condition du champ IF.
type: docs
weight: 1860
url: /fr/net/aspose.words.fields/fieldifcomparisonresult/
---
## FieldIfComparisonResult enumeration

Spécifie le résultat de l'évaluation de la condition du champ IF.

```csharp
public enum FieldIfComparisonResult
```

### Valeurs

| Nom | Évaluer | La description |
| --- | --- | --- |
| Error | `0` | Il y a une erreur dans la condition. |
| True | `1` | La condition est`vrai` . |
| False | `2` | La condition est`faux` . |

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

* espace de noms [Aspose.Words.Fields](../../aspose.words.fields/)
* Assemblée [Aspose.Words](../../)


