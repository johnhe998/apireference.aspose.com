---
title: Class Field
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Fields.Field فصل. يمثل حقل مستند Microsoft Word .
type: docs
weight: 1360
url: /ar/net/aspose.words.fields/field/
---
## Field class

يمثل حقل مستند Microsoft Word .

```csharp
public class Field
```

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

## طُرق

| اسم | وصف |
| --- | --- |
| [GetFieldCode](../../aspose.words.fields/field/getfieldcode/#getfieldcode)() | إرجاع النص بين بداية الحقل وفاصل الحقل (أو نهاية الحقل إذا لم يكن هناك فاصل) . يتم تضمين كل من رمز الحقل ونتيجة الحقل للحقول الفرعية. |
| [GetFieldCode](../../aspose.words.fields/field/getfieldcode/#getfieldcode_1)(bool) | إرجاع النص بين بداية الحقل وفاصل الحقل (أو نهاية الحقل إذا لم يكن هناك فاصل) . |
| [Remove](../../aspose.words.fields/field/remove/)() | يزيل الحقل من المستند. إرجاع عقدة بعد الحقل مباشرة. إذا كانت نهاية الحقل هي آخر child من العقدة الأصلية ، يتم إرجاع فقرته الأصلية. إذا تمت إزالة الحقل بالفعل ، يعود **لا شيء** . |
| [Unlink](../../aspose.words.fields/field/unlink/)() | يقوم بإلغاء ربط الحقل. |
| [Update](../../aspose.words.fields/field/update/#update)() | يقوم بالتحديث الميداني. يرمي إذا تم تحديث الحقل بالفعل. |
| [Update](../../aspose.words.fields/field/update/#update_1)(bool) | يقوم بإجراء تحديث ميداني. يرمي إذا تم تحديث الحقل بالفعل. |

### ملاحظات

إن الحقل في مستند Word عبارة عن بنية معقدة تتكون من عقد متعددة تتضمن بداية الحقل ، وكود الحقل ، وفاصل الحقل ، ونتيجة الحقل ونهاية الحقل. يمكن أن تكون الحقول متداخلة ، وتحتوي على محتوى غني وامتداد عدة فقرات أو أقسام في المستند. ال`Field`الفئة هي كائن "واجهة" يوفر خصائص وطرق تسمح بالعمل مع حقل ككائن واحد.

ال[`Start`](./start/) و[`Separator`](./separator/) و[`End`](./end/) تشير الخصائص إلى بداية الحقل والفاصل ونهاية الحقل على التوالي.

المحتوى بين بداية الحقل والفاصل هو رمز الحقل. المحتوى بين فاصل الحقل ونهاية الحقل هو نتيجة الحقل. يتكون رمز الحقل عادةً من واحد أو أكثر [`Run`](../../aspose.words/run/) الكائنات التي تحدد التعليمات. من المتوقع أن يقوم تطبيق المعالجة بتنفيذ كود الحقل لحساب نتيجة الحقل.

تسمى عملية حساب النتائج الميدانية التحديث الميداني. يمكن لـ Aspose.Words تحديث نتائج field لمعظم أنواع الحقول بنفس الطريقة تمامًا التي يقوم بها Microsoft Word. والأهم من ذلك ، Aspose. يمكن للكلمات حساب نتائج حتى أكثر حقول الصيغة تعقيدًا. لحساب نتيجة field لحقل واحد ، استخدم ملف[`Update`](./update/) طريقة. لتحديث الحقول في document بالكامل استخدم[`UpdateFields`](../../aspose.words/document/updatefields/).

يمكنك الحصول على إصدار النص العادي لرمز الحقل باستخدام امتداد[`GetFieldCode`](./getfieldcode/) method. يمكنك الحصول على إصدار النص العادي لنتيجة الحقل وتعيينه باستخدام ملحق[`Result`](./result/) property. يمكن أن يحتوي كل من رمز الحقل ونتيجة الحقل على محتوى معقد ، مثل الحقول المتداخلة والفقرات والأشكال والجداول وفي هذه الحالة قد ترغب في العمل مع عقد الحقول مباشرةً إذا كنت بحاجة إلى مزيد من التحكم.

لا تقوم بإنشاء مثيلات من`Field` class مباشرة. لإنشاء حقل جديد استخدم[`InsertField`](../../aspose.words/documentbuilder/insertfield/) طريقة.

### أمثلة

يوضح كيفية إدراج حقل في مستند باستخدام رمز حقل.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Field field = builder.InsertField("DATE \\@ \"dddd, MMMM dd, yyyy\"");

Assert.AreEqual(FieldType.FieldDate, field.Type);
Assert.AreEqual("DATE \\@ \"dddd, MMMM dd, yyyy\"", field.GetFieldCode());

// هذا التحميل الزائد لطريقة InsertField يقوم تلقائيًا بتحديث الحقول المدرجة.
Assert.That(DateTime.Parse(field.Result), Is.EqualTo(DateTime.Today).Within(1).Days);
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Fields](../../aspose.words.fields/)
* المجسم [Aspose.Words](../../)


