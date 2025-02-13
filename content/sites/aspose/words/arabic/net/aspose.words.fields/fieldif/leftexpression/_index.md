---
title: FieldIf.LeftExpression
second_title: Aspose.Words لمراجع .NET API
description: FieldIf ملكية. الحصول على أو تعيين الجزء الأيسر من تعبير المقارنة.
type: docs
weight: 40
url: /ar/net/aspose.words.fields/fieldif/leftexpression/
---
## FieldIf.LeftExpression property

الحصول على أو تعيين الجزء الأيسر من تعبير المقارنة.

```csharp
public string LeftExpression { get; set; }
```

### أمثلة

يوضح كيفية إدراج حقل IF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Statement 1: ");
FieldIf field = (FieldIf)builder.InsertField(FieldType.FieldIf, true);
field.LeftExpression = "0";
field.ComparisonOperator = "=";
field.RightExpression = "1";

// سيعرض الحقل IF سلسلة من خاصية "TrueText" الخاصة به ،
// أو خاصيته "FalseText" ، اعتمادًا على حقيقة البيان الذي أنشأناه.
field.TrueText = "True";
field.FalseText = "False";
field.Update();

// في هذه الحالة ، "0 = 1" غير صحيحة ، لذا ستكون النتيجة المعروضة "False".
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

// هذه المرة العبارة صحيحة ، لذا ستكون النتيجة المعروضة "صحيحة".
Assert.AreEqual(" IF  5 = \"2 + 3\" True False", field.GetFieldCode());
Assert.AreEqual(FieldIfComparisonResult.True, field.EvaluateCondition());
Assert.AreEqual("True", field.Result);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.IF.docx");
```

### أنظر أيضا

* class [FieldIf](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldif/)
* المجسم [Aspose.Words](../../../)


