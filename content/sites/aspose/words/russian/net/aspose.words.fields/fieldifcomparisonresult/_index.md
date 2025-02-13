---
title: Enum FieldIfComparisonResult
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Fields.FieldIfComparisonResult перечисление. Определяет результат оценки условия поля IF.
type: docs
weight: 1860
url: /ru/net/aspose.words.fields/fieldifcomparisonresult/
---
## FieldIfComparisonResult enumeration

Определяет результат оценки условия поля IF.

```csharp
public enum FieldIfComparisonResult
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| Error | `0` | Ошибка в условии. |
| True | `1` | Состояние`истинный` . |
| False | `2` | Состояние`ЛОЖЬ` . |

### Примеры

Показывает, как вставить поле ЕСЛИ.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Statement 1: ");
FieldIf field = (FieldIf)builder.InsertField(FieldType.FieldIf, true);
field.LeftExpression = "0";
field.ComparisonOperator = "=";
field.RightExpression = "1";

// Поле ЕСЛИ будет отображать строку либо из его свойства "TrueText",
// или его свойство "FalseText", в зависимости от истинности построенного нами утверждения.
field.TrueText = "True";
field.FalseText = "False";
field.Update();

// В этом случае "0 = 1" неверно, поэтому отображаемый результат будет "False".
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

// На этот раз утверждение верно, поэтому отображаемый результат будет «Истина».
Assert.AreEqual(" IF  5 = \"2 + 3\" True False", field.GetFieldCode());
Assert.AreEqual(FieldIfComparisonResult.True, field.EvaluateCondition());
Assert.AreEqual("True", field.Result);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.IF.docx");
```

### Смотрите также

* пространство имен [Aspose.Words.Fields](../../aspose.words.fields/)
* сборка [Aspose.Words](../../)


