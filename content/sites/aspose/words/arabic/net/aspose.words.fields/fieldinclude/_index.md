---
title: Class FieldInclude
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Fields.FieldInclude فصل. تنفذ حقل التضمين .
type: docs
weight: 1880
url: /ar/net/aspose.words.fields/fieldinclude/
---
## FieldInclude class

تنفذ حقل التضمين .

```csharp
public class FieldInclude : Field
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [FieldInclude](fieldinclude/)() | Default_Constructor |

## الخصائص

| اسم | وصف |
| --- | --- |
| [BookmarkName](../../aspose.words.fields/fieldinclude/bookmarkname/) { get; set; } | الحصول على أو تحديد اسم الإشارة المرجعية في المستند المراد تضمينه . |
| [DisplayResult](../../aspose.words.fields/field/displayresult/) { get; } | يحصل على النص الذي يمثل نتيجة الحقل المعروض. |
| [End](../../aspose.words.fields/field/end/) { get; } | يحصل على العقدة التي تمثل نهاية الحقل. |
| [Format](../../aspose.words.fields/field/format/) { get; } | يحصل على أ[`FieldFormat`](../fieldformat/) كائن يوفر وصولاً مكتوبًا إلى تنسيق الحقل. |
| [IsDirty](../../aspose.words.fields/field/isdirty/) { get; set; } | الحصول على أو تحديد ما إذا كانت النتيجة الحالية للحقل لم تعد صحيحة (قديمة) بسبب التعديلات الأخرى التي تم إجراؤها على المستند. |
| [IsLocked](../../aspose.words.fields/field/islocked/) { get; set; } | تحديد ما إذا كان الحقل مغلقًا أم لا (يجب عدم إعادة حساب النتيجة). |
| [LocaleId](../../aspose.words.fields/field/localeid/) { get; set; } | الحصول على أو تحديد LCID للحقل. |
| [LockFields](../../aspose.words.fields/fieldinclude/lockfields/) { get; set; } | يحصل أو يحدد ما إذا كان سيتم منع تحديث الحقول في المستند المضمن. |
| [Result](../../aspose.words.fields/field/result/) { get; set; } | الحصول على أو تعيين النص الموجود بين فاصل الحقل ونهاية الحقل. |
| [Separator](../../aspose.words.fields/field/separator/) { get; } | يحصل على العقدة التي تمثل فاصل المجال. يمكن أن يكون فارغًا. |
| [SourceFullName](../../aspose.words.fields/fieldinclude/sourcefullname/) { get; set; } | الحصول على أو تحديد مكان المستند. |
| [Start](../../aspose.words.fields/field/start/) { get; } | يحصل على العقدة التي تمثل بداية الحقل. |
| [TextConverter](../../aspose.words.fields/fieldinclude/textconverter/) { get; set; } | الحصول على أو تحديد اسم محول النص لتنسيق الملف المضمن. |
| virtual [Type](../../aspose.words.fields/field/type/) { get; } | يحصل على نوع حقل Microsoft Word . |

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

إدراج كل أو جزء من النص والرسومات المضمنة في مستند آخر.

### أمثلة

يوضح كيفية إنشاء حقل INCLUDE وتعيين خصائصه.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// يمكننا استخدام حقل INCLUDE لاستيراد جزء من مستند آخر في نظام الملفات المحلي.
// تحتوي الإشارة المرجعية من المستند الآخر التي نشير إليها مع هذا الحقل على هذا الجزء المستورد.
FieldInclude field = (FieldInclude)builder.InsertField(FieldType.FieldInclude, true);
field.SourceFullName = MyDir + "Bookmarks.docx";
field.BookmarkName = "MyBookmark1";
field.LockFields = false;
field.TextConverter = "Microsoft Word";

Assert.True(Regex.Match(field.GetFieldCode(), " INCLUDE .* MyBookmark1 \\\\c \"Microsoft Word\"").Success);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INCLUDE.docx");
```

### أنظر أيضا

* class [Field](../field/)
* مساحة الاسم [Aspose.Words.Fields](../../aspose.words.fields/)
* المجسم [Aspose.Words](../../)


