---
title: Class FieldPrintDate
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Fields.FieldPrintDate فصل. تنفذ حقل PRINTDATE .
type: docs
weight: 2140
url: /ar/net/aspose.words.fields/fieldprintdate/
---
## FieldPrintDate class

تنفذ حقل PRINTDATE .

```csharp
public class FieldPrintDate : Field
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [FieldPrintDate](fieldprintdate/)() | Default_Constructor |

## الخصائص

| اسم | وصف |
| --- | --- |
| [DisplayResult](../../aspose.words.fields/field/displayresult/) { get; } | يحصل على النص الذي يمثل نتيجة الحقل المعروض. |
| [End](../../aspose.words.fields/field/end/) { get; } | يحصل على العقدة التي تمثل نهاية الحقل. |
| [Format](../../aspose.words.fields/field/format/) { get; } | يحصل على أ[`FieldFormat`](../fieldformat/) كائن يوفر وصولاً مكتوبًا إلى تنسيق الحقل. |
| [IsDirty](../../aspose.words.fields/field/isdirty/) { get; set; } | الحصول على أو تحديد ما إذا كانت النتيجة الحالية للحقل لم تعد صحيحة (قديمة) بسبب التعديلات الأخرى التي تم إجراؤها على المستند. |
| [IsLocked](../../aspose.words.fields/field/islocked/) { get; set; } | تحديد ما إذا كان الحقل مغلقًا أم لا (يجب عدم إعادة حساب النتيجة). |
| [LocaleId](../../aspose.words.fields/field/localeid/) { get; set; } | الحصول على أو تحديد LCID للحقل. |
| [Result](../../aspose.words.fields/field/result/) { get; set; } | الحصول على أو تعيين النص الموجود بين فاصل الحقل ونهاية الحقل. |
| [Separator](../../aspose.words.fields/field/separator/) { get; } | يحصل على العقدة التي تمثل فاصل المجال. يمكن أن يكون فارغًا. |
| [Start](../../aspose.words.fields/field/start/) { get; } | يحصل على العقدة التي تمثل بداية الحقل. |
| virtual [Type](../../aspose.words.fields/field/type/) { get; } | يحصل على نوع حقل Microsoft Word . |
| [UseLunarCalendar](../../aspose.words.fields/fieldprintdate/uselunarcalendar/) { get; set; } | يحصل أو يحدد ما إذا كان سيتم استخدام التقويم الهجري القمري أو التقويم القمري العبري. |
| [UseSakaEraCalendar](../../aspose.words.fields/fieldprintdate/usesakaeracalendar/) { get; set; } | يحصل أو يحدد ما إذا كان سيتم استخدام تقويم Saka Era . |
| [UseUmAlQuraCalendar](../../aspose.words.fields/fieldprintdate/useumalquracalendar/) { get; set; } | الحصول على أو تحديد ما إذا كان سيتم استخدام تقويم أم القرى. |

## طُرق

| اسم | وصف |
| --- | --- |
| [GetFieldCode](../../aspose.words.fields/field/getfieldcode/)() | إرجاع النص بين بداية الحقل وفاصل الحقل (أو نهاية الحقل إذا لم يكن هناك فاصل) . يتم تضمين كل من رمز الحقل ونتيجة الحقل للحقول الفرعية. |
| [GetFieldCode](../../aspose.words.fields/field/getfieldcode/)(bool) | إرجاع النص بين بداية الحقل وفاصل الحقل (أو نهاية الحقل إذا لم يكن هناك فاصل) . |
| [Remove](../../aspose.words.fields/field/remove/)() | يزيل الحقل من المستند. إرجاع عقدة بعد الحقل مباشرة. إذا كانت نهاية الحقل هي آخر child من العقدة الأصلية ، يتم إرجاع فقرته الأصلية. إذا تمت إزالة الحقل بالفعل ، يعود **لا شيء** . |
| [Unlink](../../aspose.words.fields/field/unlink/)() | يقوم بإلغاء ربط الحقل. |
| [Update](../../aspose.words.fields/field/update/)() | يقوم بالتحديث الميداني. يرمي إذا تم تحديث الحقل بالفعل. |
| [Update](../../aspose.words.fields/field/update/)(bool) | يقوم بإجراء تحديث ميداني. يرمي إذا تم تحديث الحقل بالفعل. |

### ملاحظات

استرداد تاريخ ووقت آخر طباعة للمستند. بشكل افتراضي ، يتم استخدام التقويم الميلادي.

### أمثلة

يظهر قراءة حقول PRINTDATE.

```csharp
Document doc = new Document(MyDir + "Field sample - PRINTDATE.docx");

// عند طباعة مستند بواسطة طابعة أو طباعته كملف PDF (لكن لا يتم تصديره إلى PDF) ،
// ستعرض حقول PRINTDATE تاريخ / وقت عملية الطباعة.
// في حالة عدم إجراء طباعة ، ستعرض هذه الحقول "0/0/0000".
FieldPrintDate field = (FieldPrintDate)doc.Range.Fields[0];

Assert.AreEqual("3/25/2020 12:00:00 AM", field.Result);
Assert.AreEqual(" PRINTDATE ", field.GetFieldCode());

// فيما يلي ثلاثة أنواع تقويم مختلفة وفقًا لحقل PRINTDATE
// يمكنه عرض تاريخ ووقت آخر عملية طباعة.
// 1 - التقويم القمري الإسلامي:
field = (FieldPrintDate)doc.Range.Fields[1];

Assert.True(field.UseLunarCalendar);
Assert.AreEqual("8/1/1441 12:00:00 AM", field.Result);
Assert.AreEqual(" PRINTDATE  \\h", field.GetFieldCode());

field = (FieldPrintDate)doc.Range.Fields[2];

// 2 - تقويم أم القرى:
Assert.True(field.UseUmAlQuraCalendar);
Assert.AreEqual("8/1/1441 12:00:00 AM", field.Result);
Assert.AreEqual(" PRINTDATE  \\u", field.GetFieldCode());

field = (FieldPrintDate)doc.Range.Fields[3];

// 3 - التقويم الوطني الهندي:
Assert.True(field.UseSakaEraCalendar);
Assert.AreEqual("1/5/1942 12:00:00 AM", field.Result);
Assert.AreEqual(" PRINTDATE  \\s", field.GetFieldCode());
```

### أنظر أيضا

* class [Field](../field/)
* مساحة الاسم [Aspose.Words.Fields](../../aspose.words.fields/)
* المجسم [Aspose.Words](../../)


