---
title: Class FieldArgumentBuilder
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Fields.FieldArgumentBuilder فصل. إنشاء وسيطة حقل معقدة تتكون من حقول وعقد ونص عادي.
type: docs
weight: 1400
url: /ar/net/aspose.words.fields/fieldargumentbuilder/
---
## FieldArgumentBuilder class

إنشاء وسيطة حقل معقدة تتكون من حقول وعقد ونص عادي.

```csharp
public class FieldArgumentBuilder
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [FieldArgumentBuilder](fieldargumentbuilder/)() | يقوم بتهيئة مثيل لملف`FieldArgumentBuilder` فئة . |

## طُرق

| اسم | وصف |
| --- | --- |
| [AddField](../../aspose.words.fields/fieldargumentbuilder/addfield/)(FieldBuilder) | يضيف حقلاً يمثله ملف[`FieldBuilder`](../fieldbuilder/) للحجة. |
| [AddNode](../../aspose.words.fields/fieldargumentbuilder/addnode/)(Inline) | يضيف عقدة إلى الوسيطة . |
| [AddText](../../aspose.words.fields/fieldargumentbuilder/addtext/)(string) | إضافة نص عادي إلى الوسيطة . |

### أمثلة

يوضح كيفية إنشاء الحقول باستخدام منشئ الحقول ، ثم إدراجها في المستند.

```csharp
Document doc = new Document();

// فيما يلي ثلاثة أمثلة على إنشاء الحقل باستخدام منشئ الحقل.
// 1 - حقل واحد:
// استخدم منشئ الحقول لإضافة حقل SYMBOL الذي يعرض الرمز ƒ (Florin).
FieldBuilder builder = new FieldBuilder(FieldType.FieldSymbol);
builder.AddArgument(402);
builder.AddSwitch("\\f", "Arial");
builder.AddSwitch("\\s", 25);
builder.AddSwitch("\\u");
Field field = builder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);

Assert.AreEqual(" SYMBOL 402 \\f Arial \\s 25 \\u ", field.GetFieldCode());

// 2 - الحقل المتداخل:
// استخدم منشئ الحقل لإنشاء حقل صيغة يُستخدم كحقل داخلي بواسطة مُنشئ حقل آخر.
FieldBuilder innerFormulaBuilder = new FieldBuilder(FieldType.FieldFormula);
innerFormulaBuilder.AddArgument(100);
innerFormulaBuilder.AddArgument("+");
innerFormulaBuilder.AddArgument(74);

// أنشئ منشئًا آخر لحقل SYMBOL آخر ، وأدخل حقل الصيغة
 // التي أنشأناها أعلاه في حقل SYMBOL كحجة لها.
builder = new FieldBuilder(FieldType.FieldSymbol);
builder.AddArgument(innerFormulaBuilder);
field = builder.BuildAndInsert(doc.FirstSection.Body.AppendParagraph(string.Empty));

// سيستخدم حقل SYMBOL الخارجي نتيجة حقل الصيغة ، 174 ، كوسيطة لها ،
// مما سيجعل الحقل يعرض رمز ® (علامة مسجلة) نظرًا لأن رقم حرفه هو 174.
Assert.AreEqual(" SYMBOL \u0013 = 100 + 74 \u0014\u0015 ", field.GetFieldCode());

// 3 - الحقول والوسيطات المتعددة المتداخلة:
// الآن ، سنستخدم أداة إنشاء لإنشاء حقل IF ، والذي يعرض إحدى قيمتي السلسلة المخصصتين ،
// اعتمادًا على قيمة صواب / خطأ لتعبيرها. للحصول على قيمة صواب / خطأ
// الذي يحدد السلسلة التي يعرضها حقل IF ، سيختبر حقل IF تعبيرين رقميين للتساوي.
// سنقدم التعبيرين في شكل حقول معادلة ، والتي سنقوم بتداخلها داخل حقل IF.
FieldBuilder leftExpression = new FieldBuilder(FieldType.FieldFormula);
leftExpression.AddArgument(2);
leftExpression.AddArgument("+");
leftExpression.AddArgument(3);

FieldBuilder rightExpression = new FieldBuilder(FieldType.FieldFormula);
rightExpression.AddArgument(2.5);
rightExpression.AddArgument("*");
rightExpression.AddArgument(5.2);

// بعد ذلك ، سنقوم ببناء وسيطتي حقل ، والتي ستكون بمثابة سلاسل إخراج صحيحة / خاطئة لحقل IF.
// ستعيد هذه الوسيطات استخدام القيم الناتجة لتعبيراتنا الرقمية.
FieldArgumentBuilder trueOutput = new FieldArgumentBuilder();
trueOutput.AddText("True, both expressions amount to ");
trueOutput.AddField(leftExpression);

FieldArgumentBuilder falseOutput = new FieldArgumentBuilder();
falseOutput.AddNode(new Run(doc, "False, "));
falseOutput.AddField(leftExpression);
falseOutput.AddNode(new Run(doc, " does not equal "));
falseOutput.AddField(rightExpression);

 // أخيرًا ، سننشئ منشئ حقل آخر لحقل IF ودمج كل التعبيرات.
builder = new FieldBuilder(FieldType.FieldIf);
builder.AddArgument(leftExpression);
builder.AddArgument("=");
builder.AddArgument(rightExpression);
builder.AddArgument(trueOutput);
builder.AddArgument(falseOutput);
field = builder.BuildAndInsert(doc.FirstSection.Body.AppendParagraph(string.Empty));

Assert.AreEqual(" IF \u0013 = 2 + 3 \u0014\u0015 = \u0013 = 2.5 * 5.2 \u0014\u0015 " +
                "\"True, both expressions amount to \u0013 = 2 + 3 \u0014\u0015\" " +
                "\"False, \u0013 = 2 + 3 \u0014\u0015 does not equal \u0013 = 2.5 * 5.2 \u0014\u0015\" ", field.GetFieldCode());

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.SYMBOL.docx");
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Fields](../../aspose.words.fields/)
* المجسم [Aspose.Words](../../)


